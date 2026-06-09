# CIcmColorContext::OpenColorProfileW(MilIccProfile *,void * *)

- ea: `0x18002ad70`
- end: `0x18002ae2a`
- name: `?OpenColorProfileW@CIcmColorContext@@UEAAJPEAUMilIccProfile@@PEAPEAX@Z`
- size: `186`
- prototype: `int(CIcmColorContext *__hidden this, struct MilIccProfile *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800058c0`
- `0x180007410`
- `0x18000f1d0`
- `0x180011760`
- `0x180013390`
- `0x180013ab8`
- `0x1800171c4`
- `0x18002ad70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002addc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002addc`

## pseudocode

```c
__int64 __fastcall CIcmColorContext::OpenColorProfileW(CIcmColorContext *this, struct tagPROFILE *a2, void **a3)
{
  signed int v6; // ebx
  void **v7; // rdi
  unsigned int v8; // edx
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  signed int LastError; // eax
  char *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = (char *)this - 56;
  v6 = -2147024809;
  CMTALock::Enter((CIcmColorContext *)((char *)this - 56));
  v7 = (void **)((char *)this + 8);
  if ( ICMModule::EnsureLoaded() )
  {
    if ( *v7 )
      ICMModule::CloseColorProfile(*v7);
    *v7 = ICMModule::OpenColorProfileW(a2, v8, v9, v10);
  }
  if ( *v7 )
  {
    if ( (unsigned int)ICMModule::GetColorProfileHeader(*v7, (struct tagPROFILEHEADER *)((char *)this + 16)) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  *a3 = *v7;
  if ( v6 < 0 && g_doStackCaptures )
    DoStackCapture(v6);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002ad70  mov     [rsp+arg_8], rbx
0x18002ad75  mov     [rsp+arg_10], rbp
0x18002ad7a  push    rsi
0x18002ad7b  push    rdi
0x18002ad7c  push    r14
0x18002ad7e  sub     rsp, 20h
0x18002ad82  mov     rsi, rcx
0x18002ad85  mov     r14, r8
0x18002ad88  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x18002ad8c  mov     rbp, rdx
0x18002ad8f  mov     [rsp+38h+arg_0], rcx
0x18002ad94  mov     ebx, 80070057h
0x18002ad99  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002ad9e  lea     rdi, [rsi+8]
0x18002ada2  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x18002ada7  test    eax, eax
0x18002ada9  jz      short loc_18002ADC3
0x18002adab  mov     rcx, [rdi]; void *
0x18002adae  test    rcx, rcx
0x18002adb1  jz      short loc_18002ADB8
0x18002adb3  call    ?CloseColorProfile@ICMModule@@SAHPEAX@Z; ICMModule::CloseColorProfile(void *)
0x18002adb8  mov     rcx, rbp; struct tagPROFILE *
0x18002adbb  call    ?OpenColorProfileW@ICMModule@@SAPEAXPEAUtagPROFILE@@KKK@Z; ICMModule::OpenColorProfileW(tagPROFILE *,ulong,ulong,ulong)
0x18002adc0  mov     [rdi], rax
0x18002adc3  mov     rcx, [rdi]; void *
0x18002adc6  test    rcx, rcx
0x18002adc9  jz      short loc_18002ADF1
0x18002adcb  lea     rdx, [rsi+10h]; struct tagPROFILEHEADER *
0x18002adcf  call    ?GetColorProfileHeader@ICMModule@@SAHPEAXPEAUtagPROFILEHEADER@@@Z; ICMModule::GetColorProfileHeader(void *,tagPROFILEHEADER *)
0x18002add4  test    eax, eax
0x18002add6  jz      short loc_18002ADDC
0x18002add8  xor     ebx, ebx
0x18002adda  jmp     short loc_18002ADF1
0x18002addc  call    cs:__imp_GetLastError
0x18002ade2  mov     ebx, eax
0x18002ade4  test    eax, eax
0x18002ade6  jle     short loc_18002ADF1
0x18002ade8  movzx   ebx, ax
0x18002adeb  or      ebx, 80070000h
0x18002adf1  mov     rcx, [rdi]
0x18002adf4  mov     [r14], rcx
0x18002adf7  test    ebx, ebx
0x18002adf9  jns     short loc_18002AE0B
0x18002adfb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002ae02  jz      short loc_18002AE0B
0x18002ae04  mov     ecx, ebx; int
0x18002ae06  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002ae0b  lea     rcx, [rsp+38h+arg_0]
0x18002ae10  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002ae15  mov     rbp, [rsp+38h+arg_10]
0x18002ae1a  mov     eax, ebx
0x18002ae1c  mov     rbx, [rsp+38h+arg_8]
0x18002ae21  add     rsp, 20h
0x18002ae25  pop     r14
0x18002ae27  pop     rdi
0x18002ae28  pop     rsi
0x18002ae29  retn
```
