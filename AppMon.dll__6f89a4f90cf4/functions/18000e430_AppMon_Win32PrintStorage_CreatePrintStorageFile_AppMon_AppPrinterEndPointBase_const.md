# AppMon::Win32PrintStorage::CreatePrintStorageFile(AppMon::AppPrinterEndPointBase const *)

- ea: `0x18000e430`
- end: `0x18000e4c6`
- name: `?CreatePrintStorageFile@Win32PrintStorage@AppMon@@UEAAJPEBVAppPrinterEndPointBase@2@@Z`
- size: `150`
- prototype: `__int64 __fastcall(AppMon::Win32PrintStorage *__hidden this, const struct AppMon::AppPrinterEndPointBase *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000dfb8`
- `0x18000e430`

## pseudocode

```c
__int64 __fastcall AppMon::Win32PrintStorage::CreatePrintStorageFile(
        AppMon::Win32PrintStorage *this,
        const struct AppMon::AppPrinterEndPointBase *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF
  const struct AppMon::AppPrinterEndPointBase *v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids);
  v6[0] = this;
  v6[1] = &v7;
  v3 = AppMon::CaptureAndConvertExceptionToHR__lambda_8e55008a85a620f9e1d693e560cfd5db___(v6);
  v4 = v3;
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids,
      (unsigned int)v3);
  return v4;
}

```

## disassembly

```asm
0x18000e430  mov     [rsp+arg_0], rbx
0x18000e435  mov     [rsp+arg_8], rdx
0x18000e43a  push    rdi
0x18000e43b  sub     rsp, 30h
0x18000e43f  mov     rbx, rcx
0x18000e442  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e449  lea     rdi, WPP_GLOBAL_Control
0x18000e450  cmp     rcx, rdi
0x18000e453  jz      short loc_18000E470
0x18000e455  test    byte ptr [rcx+1Ch], 1
0x18000e459  jz      short loc_18000E470
0x18000e45b  mov     rcx, [rcx+10h]
0x18000e45f  lea     r8, WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids
0x18000e466  mov     edx, 0Ch
0x18000e46b  call    WPP_SF_
0x18000e470  lea     rax, [rsp+38h+arg_8]
0x18000e475  mov     [rsp+38h+var_18], rbx
0x18000e47a  lea     rcx, [rsp+38h+var_18]
0x18000e47f  mov     [rsp+38h+var_10], rax
0x18000e484  call    AppMon__CaptureAndConvertExceptionToHR__lambda_8e55008a85a620f9e1d693e560cfd5db___
0x18000e489  mov     ebx, eax
0x18000e48b  test    eax, eax
0x18000e48d  jns     short loc_18000E4B9
0x18000e48f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e496  cmp     rcx, rdi
0x18000e499  jz      short loc_18000E4B9
0x18000e49b  test    byte ptr [rcx+1Ch], 8
0x18000e49f  jz      short loc_18000E4B9
0x18000e4a1  mov     rcx, [rcx+10h]
0x18000e4a5  lea     r8, WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids
0x18000e4ac  mov     edx, 0Eh
0x18000e4b1  mov     r9d, eax
0x18000e4b4  call    WPP_SF_d
0x18000e4b9  mov     eax, ebx
0x18000e4bb  mov     rbx, [rsp+38h+arg_0]
0x18000e4c0  add     rsp, 30h
0x18000e4c4  pop     rdi
0x18000e4c5  retn
```
