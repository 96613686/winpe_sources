# AppMon::PortManager::DeleteAppPrinterEndPoint(ushort const *)

- ea: `0x18000ce34`
- end: `0x18000cec2`
- name: `?DeleteAppPrinterEndPoint@PortManager@AppMon@@CAJPEBG@Z`
- size: `142`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b89c`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a438`
- `0x18000ce34`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::DeleteAppPrinterEndPoint(const unsigned __int16 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  const unsigned __int16 *v4; // [rsp+30h] [rbp+8h] BYREF
  const unsigned __int16 **v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v5 = &v4;
  v1 = AppMon::CaptureAndConvertExceptionToHR__lambda_d60ee1793a04365fc3b1c94b62252af8___(&v5);
  v2 = v1;
  if ( v1 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v1);
  return v2;
}

```

## disassembly

```asm
0x18000ce34  mov     [rsp+arg_10], rbx
0x18000ce39  mov     [rsp+arg_0], rcx
0x18000ce3e  push    rdi
0x18000ce3f  sub     rsp, 20h
0x18000ce43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce4a  lea     rdi, WPP_GLOBAL_Control
0x18000ce51  cmp     rcx, rdi
0x18000ce54  jz      short loc_18000CE71
0x18000ce56  test    byte ptr [rcx+1Ch], 1
0x18000ce5a  jz      short loc_18000CE71
0x18000ce5c  mov     rcx, [rcx+10h]
0x18000ce60  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000ce67  mov     edx, 1Eh
0x18000ce6c  call    WPP_SF_
0x18000ce71  lea     rax, [rsp+28h+arg_0]
0x18000ce76  lea     rcx, [rsp+28h+arg_8]
0x18000ce7b  mov     [rsp+28h+arg_8], rax
0x18000ce80  call    AppMon__CaptureAndConvertExceptionToHR__lambda_d60ee1793a04365fc3b1c94b62252af8___
0x18000ce85  mov     ebx, eax
0x18000ce87  test    eax, eax
0x18000ce89  jns     short loc_18000CEB5
0x18000ce8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce92  cmp     rcx, rdi
0x18000ce95  jz      short loc_18000CEB5
0x18000ce97  test    byte ptr [rcx+1Ch], 8
0x18000ce9b  jz      short loc_18000CEB5
0x18000ce9d  mov     rcx, [rcx+10h]
0x18000cea1  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cea8  mov     edx, 1Fh
0x18000cead  mov     r9d, eax
0x18000ceb0  call    WPP_SF_d
0x18000ceb5  mov     eax, ebx
0x18000ceb7  mov     rbx, [rsp+28h+arg_10]
0x18000cebc  add     rsp, 20h
0x18000cec0  pop     rdi
0x18000cec1  retn
```
