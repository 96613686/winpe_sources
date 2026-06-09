# CAxInstaller::WinVerifyFile2(ushort const *,ushort const *)

- ea: `0x180006e30`
- end: `0x180006e9a`
- name: `?WinVerifyFile2@CAxInstaller@@QEAAJPEBG0@Z`
- size: `106`
- prototype: `int(CAxInstaller *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180005ee0`

## callees

- `0x180006e30`
- `0x18000725c`
- `0x1800138f0`

## string_xrefs

- `0x180006e65`: `GetTokenForAxIS failed with  0x%x`

## pseudocode

```c
__int64 __fastcall CAxInstaller::WinVerifyFile2(
        CAxInstaller *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  _QWORD *v3; // rbx
  __int64 result; // rax
  unsigned int v5; // [rsp+20h] [rbp-28h]
  __int64 v6; // [rsp+20h] [rbp-28h]
  int v7; // [rsp+28h] [rbp-20h]

  v3 = (_QWORD *)((char *)this + 712);
  result = AicGetTokenForAxIS(*((HWND *)this + 86), a2, a3, a2, v5, v7, *((HANDLE *)this + 85), (void **)this + 89);
  if ( (_DWORD)result )
  {
    LODWORD(v6) = result;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"GetTokenForAxIS failed with  0x%x", v6);
    return 2148204548LL;
  }
  else if ( !*v3 )
  {
    return 2147942405LL;
  }
  return result;
}

```

## disassembly

```asm
0x180006e30  push    rbx
0x180006e32  sub     rsp, 40h
0x180006e36  lea     rbx, [rcx+2C8h]
0x180006e3d  mov     [rsp+48h+var_10], rbx; void **
0x180006e42  mov     rax, [rcx+2A8h]
0x180006e49  mov     [rsp+48h+hToken], rax; hToken
0x180006e4e  mov     r9, rdx; unsigned __int16 *
0x180006e51  mov     rcx, [rcx+2B0h]; HWND
0x180006e58  call    ?AicGetTokenForAxIS@@YAJPEAUHWND__@@PEBG11KHPEAXPEAPEAX@Z; AicGetTokenForAxIS(HWND__ *,ushort const *,ushort const *,ushort const *,ulong,int,void *,void * *)
0x180006e5d  test    eax, eax
0x180006e5f  jz      short loc_180006E88
0x180006e61  mov     dword ptr [rsp+48h+var_28], eax
0x180006e65  lea     r9, aGettokenforaxi; "GetTokenForAxIS failed with  0x%x"
0x180006e6c  mov     edx, 8; unsigned int
0x180006e71  lea     r8d, [rdx-6]; unsigned __int8
0x180006e75  lea     rcx, qword_180021AD8; this
0x180006e7c  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180006e81  mov     eax, 800B0004h
0x180006e86  jmp     short loc_180006E94
0x180006e88  mov     ecx, 80070005h
0x180006e8d  cmp     qword ptr [rbx], 0
0x180006e91  cmovz   eax, ecx
0x180006e94  add     rsp, 40h
0x180006e98  pop     rbx
0x180006e99  retn
0x18001484f  push    rbp
0x180014851  sub     rsp, 40h
0x180014855  mov     rbp, rdx
0x180014858  add     rsp, 40h
0x18001485c  pop     rbp
0x18001485d  retn
```
