# CIcmColorTransform::GetColorDirectoryW(ushort const *,ushort *,ulong *)

- ea: `0x18002a940`
- end: `0x18002a9c2`
- name: `?GetColorDirectoryW@CIcmColorTransform@@UEAAJPEBGPEAGPEAK@Z`
- size: `130`
- prototype: `int(CIcmColorTransform *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800058c0`
- `0x180007410`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18002a940`
- `0x18002ae30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a984`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::GetColorDirectoryW(
        CIcmColorTransform *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  signed int v7; // ebx
  signed int LastError; // eax
  char *v10; // [rsp+50h] [rbp+8h] BYREF

  v10 = (char *)this - 80;
  v7 = -2147024809;
  CMTALock::Enter((CIcmColorTransform *)((char *)this - 80));
  if ( !ICMModule::EnsureLoaded() )
    goto LABEL_7;
  if ( (unsigned int)ICMModule::GetColorDirectoryW(a2, a3, a4) )
  {
    v7 = 0;
    goto LABEL_9;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 < 0 )
  {
LABEL_7:
    if ( g_doStackCaptures )
      DoStackCapture(v7);
  }
LABEL_9:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a940  push    rbx
0x18002a942  push    rbp
0x18002a943  push    rsi
0x18002a944  push    rdi
0x18002a945  sub     rsp, 28h
0x18002a949  add     rcx, 0FFFFFFFFFFFFFFB0h; this
0x18002a94d  mov     rdi, r9
0x18002a950  mov     [rsp+48h+arg_0], rcx
0x18002a955  mov     rsi, r8
0x18002a958  mov     rbp, rdx
0x18002a95b  mov     ebx, 80070057h
0x18002a960  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002a965  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x18002a96a  test    eax, eax
0x18002a96c  jz      short loc_18002A99D
0x18002a96e  mov     r8, rdi; unsigned int *
0x18002a971  mov     rdx, rsi; unsigned __int16 *
0x18002a974  mov     rcx, rbp; unsigned __int16 *
0x18002a977  call    ?GetColorDirectoryW@ICMModule@@SAHPEBGPEAGPEAK@Z; ICMModule::GetColorDirectoryW(ushort const *,ushort *,ulong *)
0x18002a97c  test    eax, eax
0x18002a97e  jz      short loc_18002A984
0x18002a980  xor     ebx, ebx
0x18002a982  jmp     short loc_18002A9AD
0x18002a984  call    cs:__imp_GetLastError
0x18002a98a  mov     ebx, eax
0x18002a98c  test    eax, eax
0x18002a98e  jle     short loc_18002A999
0x18002a990  movzx   ebx, ax
0x18002a993  or      ebx, 80070000h
0x18002a999  test    ebx, ebx
0x18002a99b  jns     short loc_18002A9AD
0x18002a99d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002a9a4  jz      short loc_18002A9AD
0x18002a9a6  mov     ecx, ebx; int
0x18002a9a8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002a9ad  lea     rcx, [rsp+48h+arg_0]
0x18002a9b2  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002a9b7  mov     eax, ebx
0x18002a9b9  add     rsp, 28h
0x18002a9bd  pop     rdi
0x18002a9be  pop     rsi
0x18002a9bf  pop     rbp
0x18002a9c0  pop     rbx
0x18002a9c1  retn
```
