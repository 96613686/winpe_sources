# NLG::FindProof::CheckWithPrefix(ushort const *)

- ea: `0x180041ecc`
- end: `0x18004207f`
- name: `?CheckWithPrefix@FindProof@NLG@@QEAA_NPEBG@Z`
- size: `435`
- prototype: `char __fastcall(NLG::FindProof *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004952c`

## callees

- `0x180017858`
- `0x180035640`
- `0x18003ed6c`
- `0x180041ecc`

## import_xrefs

- `msvcrt!_waccess` at `0x18004204f`
- `msvcrt!_waccess` at `0x18004205f`
- `msvcrt!_waccess` at `0x18004204f`
- `msvcrt!_waccess` at `0x18004205f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall NLG::FindProof::CheckWithPrefix(NLG::FindProof *this, const unsigned __int16 *a2)
{
  __int64 v4; // rcx
  unsigned __int64 v6; // rdx
  char v7; // bl
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v12; // [rsp+20h] [rbp-58h]
  __int64 v13; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-48h] BYREF
  const void *retaddr; // [rsp+78h] [rbp+0h]

  v4 = *((_QWORD *)this + 4);
  v6 = *((int *)this + 4);
  if ( *((_DWORD *)this + 7) == 3 )
  {
    v12 = *((_WORD *)this + 12) & 0x3FF | 0x400;
    v7 = 0;
    if ( StringCchPrintfW(*(unsigned __int16 **)this, v6, L"%s%d\\%s", a2, v12, v4) < 0 )
    {
      LODWORD(v13) = *((_WORD *)this + 12) & 0x3FF | 0x400;
      v8 = StringCchPrintfW(*(unsigned __int16 **)this, *((int *)this + 4), L"%s%d\\%s", a2, v13, *((_QWORD *)this + 4));
      CNLException::CNLException((CNLException *)pExceptionObject, v8, retaddr);
      throw (CNLException *)pExceptionObject;
    }
  }
  else
  {
    v7 = 0;
    if ( StringCchPrintfW(*(unsigned __int16 **)this, v6, L"%s%s", a2, v4) < 0 )
    {
      v9 = StringCchPrintfW(*(unsigned __int16 **)this, *((int *)this + 4), L"%s%s", a2, *((_QWORD *)this + 4));
      CNLException::CNLException((CNLException *)pExceptionObject, v9, retaddr);
      throw (CNLException *)pExceptionObject;
    }
  }
  if ( StringCchPrintfW(*((unsigned __int16 **)this + 1), *((int *)this + 5), L"%s%s", a2, *((_QWORD *)this + 5)) < 0 )
  {
    v10 = StringCchPrintfW(*((unsigned __int16 **)this + 1), *((int *)this + 5), L"%s%s", a2, *((_QWORD *)this + 5));
    CNLException::CNLException((CNLException *)pExceptionObject, v10, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  if ( !_waccess(*(const wchar_t **)this, 4) && !_waccess(*((const wchar_t **)this + 1), 4) )
    return 1;
  return v7;
}

```

## disassembly

```asm
0x180041ecc  mov     [rsp+arg_0], rbx
0x180041ed1  mov     [rsp+arg_8], rsi
0x180041ed6  push    rdi
0x180041ed7  sub     rsp, 70h
0x180041edb  mov     rdi, rcx
0x180041ede  mov     rsi, rdx
0x180041ee1  mov     rcx, [rcx+20h]
0x180041ee5  mov     r9, rsi
0x180041ee8  cmp     dword ptr [rdi+1Ch], 3
0x180041eec  movsxd  rdx, dword ptr [rdi+10h]; unsigned __int64
0x180041ef0  jnz     loc_180041F7C
0x180041ef6  movzx   eax, word ptr [rdi+18h]
0x180041efa  lea     r8, aSDS; "%s%d\\%s"
0x180041f01  mov     [rsp+78h+var_50], rcx
0x180041f06  and     eax, 3FFh
0x180041f0b  mov     rcx, [rdi]; unsigned __int16 *
0x180041f0e  bts     eax, 0Ah
0x180041f12  mov     dword ptr [rsp+78h+var_58], eax
0x180041f16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041f1b  xor     ebx, ebx
0x180041f1d  test    eax, eax
0x180041f1f  jns     loc_180041FDB
0x180041f25  movzx   ecx, word ptr [rdi+18h]
0x180041f29  lea     r8, aSDS; "%s%d\\%s"
0x180041f30  mov     rax, [rdi+20h]
0x180041f34  and     ecx, 3FFh
0x180041f3a  movsxd  rdx, dword ptr [rdi+10h]; unsigned __int64
0x180041f3e  bts     ecx, 0Ah
0x180041f42  mov     rbx, [rsp+78h]
0x180041f47  mov     r9, rsi
0x180041f4a  mov     [rsp+78h+var_50], rax
0x180041f4f  mov     dword ptr [rsp+78h+var_58], ecx
0x180041f53  mov     rcx, [rdi]; unsigned __int16 *
0x180041f56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041f5b  mov     edx, eax; int
0x180041f5d  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180041f62  mov     r8, rbx; void *
0x180041f65  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180041f6a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180041f71  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180041f76  call    _CxxThrowException_0
0x180041f7c  mov     [rsp+78h+var_58], rcx
0x180041f81  lea     r8, aSS; "%s%s"
0x180041f88  mov     rcx, [rdi]; unsigned __int16 *
0x180041f8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041f90  xor     ebx, ebx
0x180041f92  test    eax, eax
0x180041f94  jns     short loc_180041FDB
0x180041f96  mov     rax, [rdi+20h]
0x180041f9a  lea     r8, aSS; "%s%s"
0x180041fa1  movsxd  rdx, dword ptr [rdi+10h]; unsigned __int64
0x180041fa5  mov     r9, rsi
0x180041fa8  mov     rcx, [rdi]; unsigned __int16 *
0x180041fab  mov     rbx, [rsp+78h]
0x180041fb0  mov     [rsp+78h+var_58], rax
0x180041fb5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041fba  mov     edx, eax; int
0x180041fbc  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180041fc1  mov     r8, rbx; void *
0x180041fc4  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180041fc9  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180041fd0  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180041fd5  call    _CxxThrowException_0
0x180041fdb  mov     rax, [rdi+28h]
0x180041fdf  lea     r8, aSS; "%s%s"
0x180041fe6  movsxd  rdx, dword ptr [rdi+14h]; unsigned __int64
0x180041fea  mov     r9, rsi
0x180041fed  mov     rcx, [rdi+8]; unsigned __int16 *
0x180041ff1  mov     [rsp+78h+var_58], rax
0x180041ff6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041ffb  test    eax, eax
0x180041ffd  jns     short loc_180042045
0x180041fff  mov     rax, [rdi+28h]
0x180042003  lea     r8, aSS; "%s%s"
0x18004200a  movsxd  rdx, dword ptr [rdi+14h]; unsigned __int64
0x18004200e  mov     r9, rsi
0x180042011  mov     rcx, [rdi+8]; unsigned __int16 *
0x180042015  mov     rbx, [rsp+78h]
0x18004201a  mov     [rsp+78h+var_58], rax
0x18004201f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042024  mov     edx, eax; int
0x180042026  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18004202b  mov     r8, rbx; void *
0x18004202e  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180042033  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004203a  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18004203f  call    _CxxThrowException_0
0x180042045  mov     rcx, [rdi]; FileName
0x180042048  mov     esi, 4
0x18004204d  mov     edx, esi; AccessMode
0x18004204f  call    cs:__imp__waccess
0x180042055  test    eax, eax
0x180042057  jnz     short loc_18004206B
0x180042059  mov     rcx, [rdi+8]; FileName
0x18004205d  mov     edx, esi; AccessMode
0x18004205f  call    cs:__imp__waccess
0x180042065  test    eax, eax
0x180042067  jnz     short loc_18004206B
0x180042069  mov     bl, 1
0x18004206b  lea     r11, [rsp+78h+var_8]
0x180042070  mov     al, bl
0x180042072  mov     rbx, [r11+10h]
0x180042076  mov     rsi, [r11+18h]
0x18004207a  mov     rsp, r11
0x18004207d  pop     rdi
0x18004207e  retn
```
