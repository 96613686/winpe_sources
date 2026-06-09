# AppMon::Win32PrintStorage::WriteToStorageFile(uchar *,ulong,ulong *)

- ea: `0x18000e5c0`
- end: `0x18000e673`
- name: `?WriteToStorageFile@Win32PrintStorage@AppMon@@UEAAJPEAEKPEAK@Z`
- size: `179`
- prototype: `__int64 __fastcall(AppMon::Win32PrintStorage *this, unsigned __int8 *, int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000df88`
- `0x18000e5c0`

## pseudocode

```c
__int64 __fastcall AppMon::Win32PrintStorage::WriteToStorageFile(
        AppMon::Win32PrintStorage *this,
        unsigned __int8 *a2,
        int a3,
        unsigned int *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD v8[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int8 *v9; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+60h] [rbp+18h] BYREF
  unsigned int *v11; // [rsp+68h] [rbp+20h] BYREF

  v11 = a4;
  v10 = a3;
  v9 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids);
  v8[0] = this;
  v8[1] = &v9;
  v8[2] = &v10;
  v8[3] = &v11;
  v5 = AppMon::CaptureAndConvertExceptionToHR__lambda_8cdc80e37704e5a339876f1a63b9da8c___(v8);
  v6 = v5;
  if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids,
      (unsigned int)v5);
  return v6;
}

```

## disassembly

```asm
0x18000e5c0  mov     rax, rsp
0x18000e5c3  mov     [rax+8], rbx
0x18000e5c7  mov     [rax+20h], r9
0x18000e5cb  mov     [rax+18h], r8d
0x18000e5cf  mov     [rax+10h], rdx
0x18000e5d3  push    rdi
0x18000e5d4  sub     rsp, 40h
0x18000e5d8  mov     rbx, rcx
0x18000e5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5e2  lea     rdi, WPP_GLOBAL_Control
0x18000e5e9  cmp     rcx, rdi
0x18000e5ec  jz      short loc_18000E609
0x18000e5ee  test    byte ptr [rcx+1Ch], 1
0x18000e5f2  jz      short loc_18000E609
0x18000e5f4  mov     rcx, [rcx+10h]
0x18000e5f8  lea     r8, WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids
0x18000e5ff  mov     edx, 0Ah
0x18000e604  call    WPP_SF_
0x18000e609  lea     rax, [rsp+48h+arg_8]
0x18000e60e  mov     [rsp+48h+var_28], rbx
0x18000e613  mov     [rsp+48h+var_20], rax
0x18000e618  lea     rcx, [rsp+48h+var_28]
0x18000e61d  lea     rax, [rsp+48h+arg_10]
0x18000e622  mov     [rsp+48h+var_18], rax
0x18000e627  lea     rax, [rsp+48h+arg_18]
0x18000e62c  mov     [rsp+48h+var_10], rax
0x18000e631  call    AppMon__CaptureAndConvertExceptionToHR__lambda_8cdc80e37704e5a339876f1a63b9da8c___
0x18000e636  mov     ebx, eax
0x18000e638  test    eax, eax
0x18000e63a  jns     short loc_18000E666
0x18000e63c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e643  cmp     rcx, rdi
0x18000e646  jz      short loc_18000E666
0x18000e648  test    byte ptr [rcx+1Ch], 8
0x18000e64c  jz      short loc_18000E666
0x18000e64e  mov     rcx, [rcx+10h]
0x18000e652  lea     r8, WPP_07c3eead27a0336c67cd30f68f94bf12_Traceguids
0x18000e659  mov     edx, 0Bh
0x18000e65e  mov     r9d, eax
0x18000e661  call    WPP_SF_d
0x18000e666  mov     eax, ebx
0x18000e668  mov     rbx, [rsp+48h+arg_0]
0x18000e66d  add     rsp, 40h
0x18000e671  pop     rdi
0x18000e672  retn
```
