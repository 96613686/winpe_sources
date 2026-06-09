# ATL::CComCreator<ATL::CComObject<CPhotoPropertyStore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002800`
- end: `0x1800028df`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPhotoPropertyStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002510`

## callees

- `0x180002800`
- `0x180002a80`
- `0x180002ab0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002846`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002846`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPhotoPropertyStore>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // rdi
  int v6; // ebx
  HLOCAL v7; // rax

  if ( !a3 )
    return 2147500035LL;
  v5 = 0;
  *a3 = 0;
  v6 = -2147024882;
  v7 = LocalAlloc(0x40u, 0x158u);
  if ( v7 )
    v5 = ATL::CComObject<CPhotoPropertyStore>::CComObject<CPhotoPropertyStore>(v7);
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v5 + 40));
    if ( v6 < 0
      || (*(_BYTE *)(v5 + 80) = 1, (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v5)(v5, a2, a3)) != 0) )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, 1);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002800  mov     [rsp+arg_10], r8
0x180002805  mov     [rsp+arg_8], rdx
0x18000280a  mov     [rsp+arg_0], rcx
0x18000280f  push    rbx
0x180002810  push    rsi
0x180002811  push    rdi
0x180002812  push    r14
0x180002814  push    r15
0x180002816  sub     rsp, 30h
0x18000281a  mov     rsi, r8
0x18000281d  mov     r15, rdx
0x180002820  test    r8, r8
0x180002823  jz      loc_1800028AD
0x180002829  xor     edi, edi
0x18000282b  mov     [r8], rdi
0x18000282e  mov     ebx, 8007000Eh
0x180002833  mov     dword ptr [rsp+58h+arg_0], ebx
0x180002837  mov     [rsp+58h+arg_18], rdi
0x18000283c  mov     edx, 158h; uBytes
0x180002841  mov     ecx, 40h ; '@'; uFlags
0x180002846  call    cs:__imp_LocalAlloc
0x18000284d  nop     dword ptr [rax+rax+00h]
0x180002852  mov     [rsp+58h+var_38], rax
0x180002857  test    rax, rax
0x18000285a  jz      short loc_180002867
0x18000285c  mov     rcx, rax
0x18000285f  call    ??0?$CComObject@VCPhotoPropertyStore@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPhotoPropertyStore>::CComObject<CPhotoPropertyStore>(void *)
0x180002864  mov     rdi, rax
0x180002867  mov     [rsp+58h+arg_18], rdi
0x18000286c  test    rdi, rdi
0x18000286f  jz      short loc_18000289E
0x180002871  lea     rcx, [rdi+28h]; this
0x180002875  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000287a  mov     ebx, eax
0x18000287c  test    eax, eax
0x18000287e  js      short loc_1800028C9
0x180002880  mov     byte ptr [rdi+50h], 1
0x180002884  mov     rax, [rdi]
0x180002887  mov     r8, rsi
0x18000288a  mov     rdx, r15
0x18000288d  mov     rcx, rdi
0x180002890  mov     rax, [rax]
0x180002893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002898  mov     ebx, eax
0x18000289a  test    eax, eax
0x18000289c  jnz     short loc_1800028C9
0x18000289e  mov     eax, ebx
0x1800028a0  add     rsp, 30h
0x1800028a4  pop     r15
0x1800028a6  pop     r14
0x1800028a8  pop     rdi
0x1800028a9  pop     rsi
0x1800028aa  pop     rbx
0x1800028ab  retn
0x1800028ad  mov     eax, 80004003h
0x1800028b2  jmp     short loc_1800028A0
0x1800028b4  mov     rsi, [rsp+58h+arg_10]
0x1800028b9  mov     r15, [rsp+58h+arg_8]
0x1800028be  mov     ebx, dword ptr [rsp+58h+arg_0]
0x1800028c2  mov     rdi, [rsp+58h+arg_18]
0x1800028c7  jmp     short loc_18000286C
0x1800028c9  mov     rdx, [rdi]
0x1800028cc  mov     rax, [rdx+20h]
0x1800028d0  mov     edx, 1
0x1800028d5  mov     rcx, rdi
0x1800028d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028dd  jmp     short loc_18000289E
```
