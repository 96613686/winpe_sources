# ATL::CComCreator<ATL::CComObject<CPhotoPropertyStore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800026f0`
- end: `0x1800027c4`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPhotoPropertyStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x1800026f0`
- `0x180002960`
- `0x180002988`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002732`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002732`

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
0x1800026f0  mov     [rsp+arg_10], r8
0x1800026f5  mov     [rsp+arg_8], rdx
0x1800026fa  mov     [rsp+arg_0], rcx
0x1800026ff  push    rbx
0x180002700  push    rsi
0x180002701  push    rdi
0x180002702  push    r14
0x180002704  push    r15
0x180002706  sub     rsp, 30h
0x18000270a  mov     rsi, r8
0x18000270d  mov     r15, rdx
0x180002710  test    r8, r8
0x180002713  jz      short loc_180002792
0x180002715  xor     edi, edi
0x180002717  mov     [r8], rdi
0x18000271a  mov     ebx, 8007000Eh
0x18000271f  mov     dword ptr [rsp+58h+arg_0], ebx
0x180002723  mov     [rsp+58h+arg_18], rdi
0x180002728  mov     edx, 158h; uBytes
0x18000272d  mov     ecx, 40h ; '@'; uFlags
0x180002732  call    cs:__imp_LocalAlloc
0x180002738  mov     [rsp+58h+var_38], rax
0x18000273d  test    rax, rax
0x180002740  jz      short loc_18000274D
0x180002742  mov     rcx, rax
0x180002745  call    ??0?$CComObject@VCPhotoPropertyStore@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPhotoPropertyStore>::CComObject<CPhotoPropertyStore>(void *)
0x18000274a  mov     rdi, rax
0x18000274d  mov     [rsp+58h+arg_18], rdi
0x180002752  test    rdi, rdi
0x180002755  jz      short loc_180002784
0x180002757  lea     rcx, [rdi+28h]; this
0x18000275b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002760  mov     ebx, eax
0x180002762  test    eax, eax
0x180002764  js      short loc_1800027AE
0x180002766  mov     byte ptr [rdi+50h], 1
0x18000276a  mov     rax, [rdi]
0x18000276d  mov     r8, rsi
0x180002770  mov     rdx, r15
0x180002773  mov     rcx, rdi
0x180002776  mov     rax, [rax]
0x180002779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000277e  mov     ebx, eax
0x180002780  test    eax, eax
0x180002782  jnz     short loc_1800027AE
0x180002784  mov     eax, ebx
0x180002786  add     rsp, 30h
0x18000278a  pop     r15
0x18000278c  pop     r14
0x18000278e  pop     rdi
0x18000278f  pop     rsi
0x180002790  pop     rbx
0x180002791  retn
0x180002792  mov     eax, 80004003h
0x180002797  jmp     short loc_180002786
0x180002799  mov     rsi, [rsp+58h+arg_10]
0x18000279e  mov     r15, [rsp+58h+arg_8]
0x1800027a3  mov     ebx, dword ptr [rsp+58h+arg_0]
0x1800027a7  mov     rdi, [rsp+58h+arg_18]
0x1800027ac  jmp     short loc_180002752
0x1800027ae  mov     rdx, [rdi]
0x1800027b1  mov     rax, [rdx+20h]
0x1800027b5  mov     edx, 1
0x1800027ba  mov     rcx, rdi
0x1800027bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c2  jmp     short loc_180002784
```
