# Streaming::Utils::GetCurrentActivityID(void)

- ea: `0x1400147fc`
- end: `0x14001492d`
- name: `?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ`
- size: `305`
- prototype: `GUID **__fastcall(GUID **)`
- caller_count: `44`
- callee_count: `2`
- tags: ``

## callers

- `0x140001204`
- `0x140001780`
- `0x140001aa0`
- `0x140001e30`
- `0x1400020c8`
- `0x1400023d8`
- `0x140002edc`
- `0x14000571c`
- `0x140005e3c`
- `0x1400075d0`
- `0x140007700`
- `0x140007c24`
- `0x140007fe4`
- `0x1400084b0`
- `0x1400086a8`
- `0x140008bdc`
- `0x140008dc4`
- `0x14000935c`
- `0x14000984c`
- `0x140009d98`
- `0x14000a1f0`
- `0x14000a310`
- `0x14000abd8`
- `0x14000b0bc`
- `0x14000b32c`
- `0x14000b448`
- `0x14000b748`
- `0x14000bfe4`
- `0x14000c2ac`
- `0x14000c4ac`
- `0x14000d5a8`
- `0x14000f244`
- `0x14000f988`
- `0x140011154`
- `0x1400115cc`
- `0x140011f30`
- `0x140012b18`
- `0x1400135b4`
- `0x1400137d0`
- `0x1400138fc`
- `0x140013acc`
- `0x140013f68`
- `0x140014364`
- `0x140014a50`

## callees

- `0x1400147fc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14001488b`
- `ntoskrnl!EtwActivityIdControl` at `0x14001488b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400148c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400148c2`
- `ntoskrnl!ExAllocatePool2` at `0x140014819`
- `ntoskrnl!ExAllocatePool2` at `0x140014844`
- `ntoskrnl!ExAllocatePool2` at `0x140014819`
- `ntoskrnl!ExAllocatePool2` at `0x140014844`

## pseudocode

```c
GUID **__fastcall Streaming::Utils::GetCurrentActivityID(GUID **a1)
{
  GUID *Pool2; // rax
  GUID *v3; // rdi
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rsi

  Pool2 = (GUID *)ExAllocatePool2(64, 16, 1715758931);
  v3 = Pool2;
  if ( Pool2 )
    *Pool2 = 0;
  else
    v3 = 0;
  v4 = ExAllocatePool2(256, 24, 1715758931);
  v5 = (volatile signed __int32 *)v4;
  if ( !v4 )
  {
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    v6 = 8;
    v5 = 0;
LABEL_13:
    *a1 = 0;
    a1[1] = 0;
    if ( !v5 )
      return a1;
    goto LABEL_14;
  }
  *(_DWORD *)(v4 + 8) = 1;
  v6 = v4 + 8;
  *(_DWORD *)(v4 + 12) = 1;
  *(_QWORD *)v4 = &kernel_std::detail::sp_counted_impl_p<wchar_t>::`vftable';
  *(_QWORD *)(v4 + 16) = v3;
  if ( !*(_DWORD *)(v4 + 8) || !v3 )
    goto LABEL_13;
  if ( EtwActivityIdControl(1u, v3) >= 0 )
  {
    *a1 = v3;
    a1[1] = (GUID *)v5;
    _InterlockedIncrement((volatile signed __int32 *)v6);
  }
  else
  {
    *a1 = 0;
    a1[1] = 0;
  }
LABEL_14:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x1400147fc  push    rbx
0x1400147fe  push    rsi
0x1400147ff  push    rdi
0x140014800  push    r14
0x140014802  sub     rsp, 28h
0x140014806  mov     edx, 10h
0x14001480b  mov     r14, rcx
0x14001480e  mov     ebx, 66446753h
0x140014813  mov     r8d, ebx
0x140014816  lea     ecx, [rdx+30h]
0x140014819  call    cs:__imp_ExAllocatePool2
0x140014820  nop     dword ptr [rax+rax+00h]
0x140014825  mov     rdi, rax
0x140014828  test    rax, rax
0x14001482b  jz      short loc_140014835
0x14001482d  xorps   xmm0, xmm0
0x140014830  movups  xmmword ptr [rax], xmm0
0x140014833  jmp     short loc_140014837
0x140014835  xor     edi, edi
0x140014837  mov     r8d, ebx
0x14001483a  mov     edx, 18h
0x14001483f  mov     ecx, 100h
0x140014844  call    cs:__imp_ExAllocatePool2
0x14001484b  nop     dword ptr [rax+rax+00h]
0x140014850  mov     rbx, rax
0x140014853  test    rax, rax
0x140014856  jz      short loc_1400148B8
0x140014858  mov     dword ptr [rax+8], 1
0x14001485f  lea     rsi, [rbx+8]
0x140014863  mov     dword ptr [rax+0Ch], 1
0x14001486a  lea     rax, ??_7?$sp_counted_impl_p@_W@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<wchar_t>::`vftable'
0x140014871  mov     [rbx], rax
0x140014874  mov     [rbx+10h], rdi
0x140014878  mov     eax, [rsi]
0x14001487a  test    eax, eax
0x14001487c  jz      short loc_1400148D5
0x14001487e  test    rdi, rdi
0x140014881  jz      short loc_1400148D5
0x140014883  mov     rdx, rdi; ActivityId
0x140014886  mov     ecx, 1; ControlCode
0x14001488b  call    cs:__imp_EtwActivityIdControl
0x140014892  nop     dword ptr [rax+rax+00h]
0x140014897  test    eax, eax
0x140014899  jns     short loc_1400148AC
0x14001489b  mov     qword ptr [r14], 0
0x1400148a2  mov     qword ptr [r14+8], 0
0x1400148aa  jmp     short loc_1400148E9
0x1400148ac  mov     [r14], rdi
0x1400148af  mov     [r14+8], rbx
0x1400148b3  lock inc dword ptr [rsi]
0x1400148b6  jmp     short loc_1400148E9
0x1400148b8  test    rdi, rdi
0x1400148bb  jz      short loc_1400148CE
0x1400148bd  xor     edx, edx; Tag
0x1400148bf  mov     rcx, rdi; P
0x1400148c2  call    cs:__imp_ExFreePoolWithTag
0x1400148c9  nop     dword ptr [rax+rax+00h]
0x1400148ce  mov     esi, 8
0x1400148d3  xor     ebx, ebx
0x1400148d5  mov     qword ptr [r14], 0
0x1400148dc  mov     qword ptr [r14+8], 0
0x1400148e4  test    rbx, rbx
0x1400148e7  jz      short loc_14001491F
0x1400148e9  or      edi, 0FFFFFFFFh
0x1400148ec  mov     eax, edi
0x1400148ee  lock xadd [rsi], eax
0x1400148f2  add     eax, edi
0x1400148f4  jnz     short loc_14001491F
0x1400148f6  mov     rax, [rbx]
0x1400148f9  mov     rcx, rbx
0x1400148fc  mov     rax, [rax+8]
0x140014900  call    _guard_dispatch_icall
0x140014905  mov     eax, edi
0x140014907  lock xadd [rbx+0Ch], eax
0x14001490c  add     eax, edi
0x14001490e  jnz     short loc_14001491F
0x140014910  mov     rax, [rbx]
0x140014913  mov     rcx, rbx
0x140014916  mov     rax, [rax+10h]
0x14001491a  call    _guard_dispatch_icall
0x14001491f  mov     rax, r14
0x140014922  add     rsp, 28h
0x140014926  pop     r14
0x140014928  pop     rdi
0x140014929  pop     rsi
0x14001492a  pop     rbx
0x14001492b  retn
```
