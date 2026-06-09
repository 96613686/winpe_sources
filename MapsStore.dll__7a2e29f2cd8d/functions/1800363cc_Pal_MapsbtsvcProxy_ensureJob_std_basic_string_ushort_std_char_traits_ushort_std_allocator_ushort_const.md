# Pal::MapsbtsvcProxy::ensureJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800363cc`
- end: `0x18003647e`
- name: `?ensureJob@MapsbtsvcProxy@Pal@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `178`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180018534`
- `0x180019e20`
- `0x18001a054`
- `0x18001aefc`

## callees

- `0x1800126c4`
- `0x1800363cc`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800363e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800363e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003646d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003646d`
- `mapsbtsvc!MapsBackgroundTransferService_CreateOrFindJob` at `0x180036462`
- `mapsbtsvc!MapsBackgroundTransferService_CreateOrFindJob` at `0x180036462`
- `mapsbtsvc!MapsBackgroundTransferService_FreeJob` at `0x18003641f`
- `mapsbtsvc!MapsBackgroundTransferService_FreeJob` at `0x18003641f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Pal::MapsbtsvcProxy::ensureJob(__int64 a1, __int64 a2)
{
  int Job; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rax

  Job = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v6 = *(_QWORD *)(a1 + 48);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v7 == 1 || v7 == 3 )
    {
      Job = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 32LL))(*(_QWORD *)(a1 + 48));
    }
    else if ( (unsigned int)(v7 - 4) <= 1 )
    {
      MapsBackgroundTransferService_FreeJob(*(void **)(a1 + 48));
      *(_QWORD *)(a1 + 48) = 0;
    }
  }
  if ( !*(_QWORD *)(a1 + 48) && Job >= 0 )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    Job = MapsBackgroundTransferService_CreateOrFindJob(1, v8, 0, a1 + 48);
  }
  LeaveCriticalSection(v5);
  return (unsigned int)Job;
}

```

## disassembly

```asm
0x1800363cc  push    rbx
0x1800363ce  push    rbp
0x1800363cf  push    rsi
0x1800363d0  push    rdi
0x1800363d1  sub     rsp, 28h
0x1800363d5  mov     rbp, rdx
0x1800363d8  mov     rbx, rcx
0x1800363db  xor     edi, edi
0x1800363dd  lea     rsi, [rcx+8]
0x1800363e1  mov     [rsp+48h+arg_0], rsi
0x1800363e6  mov     rcx, rsi; lpCriticalSection
0x1800363e9  call    cs:__imp_EnterCriticalSection
0x1800363ef  nop
0x1800363f0  mov     rcx, [rbx+30h]
0x1800363f4  test    rcx, rcx
0x1800363f7  jz      short loc_180036441
0x1800363f9  mov     rax, [rcx]
0x1800363fc  mov     rax, [rax+8]
0x180036400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036405  mov     ecx, eax
0x180036407  sub     ecx, 1
0x18003640a  jz      short loc_18003642F
0x18003640c  sub     ecx, 2
0x18003640f  jz      short loc_18003642F
0x180036411  sub     ecx, 1
0x180036414  jz      short loc_18003641B
0x180036416  cmp     ecx, 1
0x180036419  jnz     short loc_180036441
0x18003641b  mov     rcx, [rbx+30h]
0x18003641f  call    cs:__imp_?MapsBackgroundTransferService_FreeJob@@YAXPEAX@Z; MapsBackgroundTransferService_FreeJob(void *)
0x180036425  mov     qword ptr [rbx+30h], 0
0x18003642d  jmp     short loc_180036441
0x18003642f  mov     rcx, [rbx+30h]
0x180036433  mov     rax, [rcx]
0x180036436  mov     rax, [rax+20h]
0x18003643a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003643f  mov     edi, eax
0x180036441  cmp     qword ptr [rbx+30h], 0
0x180036446  jnz     short loc_18003646A
0x180036448  test    edi, edi
0x18003644a  js      short loc_18003646A
0x18003644c  mov     rcx, rbp
0x18003644f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180036454  lea     r9, [rbx+30h]
0x180036458  xor     r8d, r8d
0x18003645b  mov     rdx, rax
0x18003645e  lea     ecx, [r8+1]
0x180036462  call    cs:__imp_?MapsBackgroundTransferService_CreateOrFindJob@@YAJW4MAPSBTSVC_JOB_TYPE@@PEBG1PEAPEAVIMapsBackgroundTransferJob@@@Z; MapsBackgroundTransferService_CreateOrFindJob(MAPSBTSVC_JOB_TYPE,ushort const *,ushort const *,IMapsBackgroundTransferJob * *)
0x180036468  mov     edi, eax
0x18003646a  mov     rcx, rsi; lpCriticalSection
0x18003646d  call    cs:__imp_LeaveCriticalSection
0x180036473  mov     eax, edi
0x180036475  add     rsp, 28h
0x180036479  pop     rdi
0x18003647a  pop     rsi
0x18003647b  pop     rbp
0x18003647c  pop     rbx
0x18003647d  retn
```
