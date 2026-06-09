# CImpIConvertType::CanConvert(ushort,ushort,ulong)

- ea: `0x180013600`
- end: `0x1800136b5`
- name: `?CanConvert@CImpIConvertType@@UEAAJGGK@Z`
- size: `181`
- prototype: `__int64 __fastcall(CImpIConvertType *__hidden this, unsigned __int16, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180013600`
- `0x180015fb4`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180013639`
- `KERNEL32!GetCurrentThreadId` at `0x180013639`
- `KERNEL32!LeaveCriticalSection` at `0x18001369c`
- `KERNEL32!LeaveCriticalSection` at `0x18001369c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013650`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013650`
- `MSDART!UMSEnterCSWraper` at `0x180013629`
- `MSDART!UMSEnterCSWraper` at `0x180013629`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIConvertType::CanConvert(
        CImpIConvertType *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rbx
  DWORD *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v13; // rcx

  v8 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v8);
  v9 = (DWORD *)(v8 + 8);
  if ( !*(_DWORD *)(v8 + 12) )
    *v9 = GetCurrentThreadId();
  ++*(_DWORD *)(v8 + 12);
  ++*(_DWORD *)(v8 + 16);
  SetErrorInfo(0, 0);
  if ( a4 )
    v10 = Exit(-2147217828, 0);
  else
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 64LL))(
            *((_QWORD *)this + 3),
            a2,
            a3);
  v11 = v10;
  --*(_DWORD *)(v8 + 16);
  if ( (*(_DWORD *)(v8 + 12))-- == 1 )
    *v9 = -1;
  v13 = *(_QWORD *)v8;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x180013600  mov     [rsp+arg_8], rbx
0x180013605  push    rbp
0x180013606  push    rsi
0x180013607  push    rdi
0x180013608  push    r14
0x18001360a  push    r15
0x18001360c  sub     rsp, 20h
0x180013610  mov     esi, r9d
0x180013613  movzx   r14d, r8w
0x180013617  movzx   r15d, dx
0x18001361b  mov     rbp, rcx
0x18001361e  mov     rbx, [rcx+18h]
0x180013622  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180013626  mov     rcx, rbx
0x180013629  call    cs:__imp_UMSEnterCSWraper
0x18001362f  lea     rdi, [rbx+8]
0x180013633  cmp     dword ptr [rbx+0Ch], 0
0x180013637  jnz     short loc_180013641
0x180013639  call    cs:__imp_GetCurrentThreadId
0x18001363f  mov     [rdi], eax
0x180013641  inc     dword ptr [rbx+0Ch]
0x180013644  inc     dword ptr [rbx+10h]
0x180013647  mov     [rsp+48h+arg_0], rbx
0x18001364c  xor     edx, edx; perrinfo
0x18001364e  xor     ecx, ecx; dwReserved
0x180013650  call    cs:__imp_SetErrorInfo
0x180013656  test    esi, esi
0x180013658  jz      short loc_18001366B
0x18001365a  xor     edx, edx; unsigned int
0x18001365c  mov     ecx, 80040E5Ch; int
0x180013661  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180013666  cmp     esi, 1
0x180013669  jmp     short loc_180013683
0x18001366b  mov     rcx, [rbp+18h]
0x18001366f  mov     rax, [rcx]
0x180013672  movzx   r8d, r14w
0x180013676  movzx   edx, r15w
0x18001367a  mov     rax, [rax+40h]
0x18001367e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013683  mov     esi, eax
0x180013685  or      edx, 0FFFFFFFFh
0x180013688  add     [rbx+10h], edx
0x18001368b  add     [rbx+0Ch], edx
0x18001368e  jnz     short loc_180013692
0x180013690  mov     [rdi], edx
0x180013692  mov     rcx, [rbx]
0x180013695  dec     dword ptr [rcx+30h]
0x180013698  add     rcx, 8; lpCriticalSection
0x18001369c  call    cs:__imp_LeaveCriticalSection
0x1800136a2  mov     eax, esi
0x1800136a4  mov     rbx, [rsp+48h+arg_8]
0x1800136a9  add     rsp, 20h
0x1800136ad  pop     r15
0x1800136af  pop     r14
0x1800136b1  pop     rdi
0x1800136b2  pop     rsi
0x1800136b3  pop     rbp
0x1800136b4  retn
```
