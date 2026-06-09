# NLG::FindProof::CheckCurrent(ushort *,int)

- ea: `0x180041dc8`
- end: `0x180041ec6`
- name: `?CheckCurrent@FindProof@NLG@@QEAA_NPEAGH@Z`
- size: `254`
- prototype: `bool __fastcall(NLG::FindProof *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004952c`

## callees

- `0x1800162e4`
- `0x180035640`
- `0x18003ed6c`
- `0x180041dc8`

## import_xrefs

- `msvcrt!_wgetcwd` at `0x180041ea7`
- `msvcrt!_wgetcwd` at `0x180041ea7`
- `msvcrt!_waccess` at `0x180041de1`
- `msvcrt!_waccess` at `0x180041df6`
- `msvcrt!_waccess` at `0x180041de1`
- `msvcrt!_waccess` at `0x180041df6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall NLG::FindProof::CheckCurrent(NLG::FindProof *this, unsigned __int16 *a2)
{
  int v4; // eax
  const void *v5; // r11
  int v6; // eax
  const void *v7; // r11
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( _waccess(*((const wchar_t **)this + 4), 4) || _waccess(*((const wchar_t **)this + 5), 4) )
    return 0;
  if ( StringCchCopyW(*(unsigned __int16 **)this, *((int *)this + 4), *((const unsigned __int16 **)this + 4)) < 0 )
  {
    v4 = StringCchCopyW(*(unsigned __int16 **)this, *((int *)this + 4), *((const unsigned __int16 **)this + 4));
    CNLException::CNLException((CNLException *)pExceptionObject, v4, v5);
    throw (CNLException *)pExceptionObject;
  }
  if ( StringCchCopyW(*((unsigned __int16 **)this + 1), *((int *)this + 5), *((const unsigned __int16 **)this + 5)) < 0 )
  {
    v6 = StringCchCopyW(*((unsigned __int16 **)this + 1), *((int *)this + 5), *((const unsigned __int16 **)this + 5));
    CNLException::CNLException((CNLException *)pExceptionObject, v6, v7);
    throw (CNLException *)pExceptionObject;
  }
  return !a2 || _wgetcwd(a2, 261) != 0;
}

```

## disassembly

```asm
0x180041dc8  mov     [rsp+arg_0], rbx
0x180041dcd  push    rdi
0x180041dce  sub     rsp, 60h
0x180041dd2  mov     rdi, rdx
0x180041dd5  mov     rbx, rcx
0x180041dd8  mov     rcx, [rcx+20h]; FileName
0x180041ddc  mov     edx, 4; AccessMode
0x180041de1  call    cs:__imp__waccess
0x180041de7  test    eax, eax
0x180041de9  jnz     loc_180041EB9
0x180041def  mov     rcx, [rbx+28h]; FileName
0x180041df3  lea     edx, [rax+4]; AccessMode
0x180041df6  call    cs:__imp__waccess
0x180041dfc  test    eax, eax
0x180041dfe  jnz     loc_180041EB9
0x180041e04  movsxd  rdx, dword ptr [rbx+10h]; unsigned __int64
0x180041e08  mov     r8, [rbx+20h]; unsigned __int16 *
0x180041e0c  mov     rcx, [rbx]; unsigned __int16 *
0x180041e0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041e14  test    eax, eax
0x180041e16  jns     short loc_180041E4E
0x180041e18  movsxd  rdx, dword ptr [rbx+10h]; unsigned __int64
0x180041e1c  mov     r8, [rbx+20h]; unsigned __int16 *
0x180041e20  mov     rcx, [rbx]; unsigned __int16 *
0x180041e23  mov     r11, [rsp+68h]
0x180041e28  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041e2d  mov     edx, eax; int
0x180041e2f  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180041e34  mov     r8, r11; void *
0x180041e37  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180041e3c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180041e43  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180041e48  call    _CxxThrowException_0
0x180041e4e  movsxd  rdx, dword ptr [rbx+14h]; unsigned __int64
0x180041e52  mov     r8, [rbx+28h]; unsigned __int16 *
0x180041e56  mov     rcx, [rbx+8]; unsigned __int16 *
0x180041e5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041e5f  test    eax, eax
0x180041e61  jns     short loc_180041E9A
0x180041e63  movsxd  rdx, dword ptr [rbx+14h]; unsigned __int64
0x180041e67  mov     r8, [rbx+28h]; unsigned __int16 *
0x180041e6b  mov     rcx, [rbx+8]; unsigned __int16 *
0x180041e6f  mov     r11, [rsp+68h]
0x180041e74  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041e79  mov     edx, eax; int
0x180041e7b  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180041e80  mov     r8, r11; void *
0x180041e83  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180041e88  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180041e8f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180041e94  call    _CxxThrowException_0
0x180041e9a  test    rdi, rdi
0x180041e9d  jz      short loc_180041EB5
0x180041e9f  mov     edx, 105h; SizeInWords
0x180041ea4  mov     rcx, rdi; DstBuf
0x180041ea7  call    cs:__imp__wgetcwd
0x180041ead  test    rax, rax
0x180041eb0  setnz   al
0x180041eb3  jmp     short loc_180041EBB
0x180041eb5  mov     al, 1
0x180041eb7  jmp     short loc_180041EBB
0x180041eb9  xor     al, al
0x180041ebb  mov     rbx, [rsp+68h+arg_0]
0x180041ec0  add     rsp, 60h
0x180041ec4  pop     rdi
0x180041ec5  retn
```
