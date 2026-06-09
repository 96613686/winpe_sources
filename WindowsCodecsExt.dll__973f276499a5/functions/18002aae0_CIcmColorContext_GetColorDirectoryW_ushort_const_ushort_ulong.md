# CIcmColorContext::GetColorDirectoryW(ushort const *,ushort *,ulong *)

- ea: `0x18002aae0`
- end: `0x18002ab62`
- name: `?GetColorDirectoryW@CIcmColorContext@@UEAAJPEBGPEAGPEAK@Z`
- size: `130`
- prototype: `int(CIcmColorContext *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800058c0`
- `0x180007410`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18002aae0`
- `0x18002ae30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab24`

## pseudocode

```c
__int64 __fastcall CIcmColorContext::GetColorDirectoryW(
        CIcmColorContext *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  signed int v7; // ebx
  signed int LastError; // eax
  char *v10; // [rsp+50h] [rbp+8h] BYREF

  v10 = (char *)this - 56;
  v7 = -2147024809;
  CMTALock::Enter((CIcmColorContext *)((char *)this - 56));
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
0x18002aae0  push    rbx
0x18002aae2  push    rbp
0x18002aae3  push    rsi
0x18002aae4  push    rdi
0x18002aae5  sub     rsp, 28h
0x18002aae9  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x18002aaed  mov     rdi, r9
0x18002aaf0  mov     [rsp+48h+arg_0], rcx
0x18002aaf5  mov     rsi, r8
0x18002aaf8  mov     rbp, rdx
0x18002aafb  mov     ebx, 80070057h
0x18002ab00  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002ab05  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x18002ab0a  test    eax, eax
0x18002ab0c  jz      short loc_18002AB3D
0x18002ab0e  mov     r8, rdi; unsigned int *
0x18002ab11  mov     rdx, rsi; unsigned __int16 *
0x18002ab14  mov     rcx, rbp; unsigned __int16 *
0x18002ab17  call    ?GetColorDirectoryW@ICMModule@@SAHPEBGPEAGPEAK@Z; ICMModule::GetColorDirectoryW(ushort const *,ushort *,ulong *)
0x18002ab1c  test    eax, eax
0x18002ab1e  jz      short loc_18002AB24
0x18002ab20  xor     ebx, ebx
0x18002ab22  jmp     short loc_18002AB4D
0x18002ab24  call    cs:__imp_GetLastError
0x18002ab2a  mov     ebx, eax
0x18002ab2c  test    eax, eax
0x18002ab2e  jle     short loc_18002AB39
0x18002ab30  movzx   ebx, ax
0x18002ab33  or      ebx, 80070000h
0x18002ab39  test    ebx, ebx
0x18002ab3b  jns     short loc_18002AB4D
0x18002ab3d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002ab44  jz      short loc_18002AB4D
0x18002ab46  mov     ecx, ebx; int
0x18002ab48  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002ab4d  lea     rcx, [rsp+48h+arg_0]
0x18002ab52  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002ab57  mov     eax, ebx
0x18002ab59  add     rsp, 28h
0x18002ab5d  pop     rdi
0x18002ab5e  pop     rsi
0x18002ab5f  pop     rbp
0x18002ab60  pop     rbx
0x18002ab61  retn
```
