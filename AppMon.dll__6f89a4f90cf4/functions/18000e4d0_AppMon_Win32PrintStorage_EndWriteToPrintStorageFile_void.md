# AppMon::Win32PrintStorage::EndWriteToPrintStorageFile(void)

- ea: `0x18000e4d0`
- end: `0x18000e557`
- name: `?EndWriteToPrintStorageFile@Win32PrintStorage@AppMon@@UEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(AppMon::Win32PrintStorage *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000df00`
- `0x18000e4d0`

## pseudocode

```c
__int64 __fastcall AppMon::Win32PrintStorage::EndWriteToPrintStorageFile(AppMon::Win32PrintStorage *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  AppMon::Win32PrintStorage *v5; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids);
  v5 = this;
  v2 = AppMon::CaptureAndConvertExceptionToHR__lambda_06aa3851b23ca0fcb6c3b3328ecb813c___(&v5);
  v3 = v2;
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids,
      (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x18000e4d0  mov     [rsp+arg_8], rbx
0x18000e4d5  push    rdi
0x18000e4d6  sub     rsp, 20h
0x18000e4da  mov     rbx, rcx
0x18000e4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4e4  lea     rdi, WPP_GLOBAL_Control
0x18000e4eb  cmp     rcx, rdi
0x18000e4ee  jz      short loc_18000E50B
0x18000e4f0  test    byte ptr [rcx+1Ch], 1
0x18000e4f4  jz      short loc_18000E50B
0x18000e4f6  mov     rcx, [rcx+10h]
0x18000e4fa  lea     r8, WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids
0x18000e501  mov     edx, 0Fh
0x18000e506  call    WPP_SF_
0x18000e50b  lea     rcx, [rsp+28h+arg_0]
0x18000e510  mov     [rsp+28h+arg_0], rbx
0x18000e515  call    AppMon__CaptureAndConvertExceptionToHR__lambda_06aa3851b23ca0fcb6c3b3328ecb813c___
0x18000e51a  mov     ebx, eax
0x18000e51c  test    eax, eax
0x18000e51e  jns     short loc_18000E54A
0x18000e520  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e527  cmp     rcx, rdi
0x18000e52a  jz      short loc_18000E54A
0x18000e52c  test    byte ptr [rcx+1Ch], 8
0x18000e530  jz      short loc_18000E54A
0x18000e532  mov     rcx, [rcx+10h]
0x18000e536  lea     r8, WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids
0x18000e53d  mov     edx, 10h
0x18000e542  mov     r9d, eax
0x18000e545  call    WPP_SF_d
0x18000e54a  mov     eax, ebx
0x18000e54c  mov     rbx, [rsp+28h+arg_8]
0x18000e551  add     rsp, 20h
0x18000e555  pop     rdi
0x18000e556  retn
```
