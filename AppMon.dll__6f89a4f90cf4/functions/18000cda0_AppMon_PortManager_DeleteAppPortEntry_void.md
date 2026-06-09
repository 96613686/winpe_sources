# AppMon::PortManager::DeleteAppPortEntry(void *)

- ea: `0x18000cda0`
- end: `0x18000ce2e`
- name: `?DeleteAppPortEntry@PortManager@AppMon@@SAJPEAX@Z`
- size: `142`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006a20`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a2d4`
- `0x18000cda0`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::DeleteAppPortEntry(void *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  void *v4; // [rsp+30h] [rbp+8h] BYREF
  void **v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v5 = &v4;
  v1 = AppMon::CaptureAndConvertExceptionToHR__lambda_a59a3339939b2e12a55facf6eecd8ae6___(&v5);
  v2 = v1;
  if ( v1 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v1);
  return v2;
}

```

## disassembly

```asm
0x18000cda0  mov     [rsp+arg_10], rbx
0x18000cda5  mov     [rsp+arg_0], rcx
0x18000cdaa  push    rdi
0x18000cdab  sub     rsp, 20h
0x18000cdaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdb6  lea     rdi, WPP_GLOBAL_Control
0x18000cdbd  cmp     rcx, rdi
0x18000cdc0  jz      short loc_18000CDDD
0x18000cdc2  test    byte ptr [rcx+1Ch], 1
0x18000cdc6  jz      short loc_18000CDDD
0x18000cdc8  mov     rcx, [rcx+10h]
0x18000cdcc  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cdd3  mov     edx, 1Ch
0x18000cdd8  call    WPP_SF_
0x18000cddd  lea     rax, [rsp+28h+arg_0]
0x18000cde2  lea     rcx, [rsp+28h+arg_8]
0x18000cde7  mov     [rsp+28h+arg_8], rax
0x18000cdec  call    AppMon__CaptureAndConvertExceptionToHR__lambda_a59a3339939b2e12a55facf6eecd8ae6___
0x18000cdf1  mov     ebx, eax
0x18000cdf3  test    eax, eax
0x18000cdf5  jns     short loc_18000CE21
0x18000cdf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdfe  cmp     rcx, rdi
0x18000ce01  jz      short loc_18000CE21
0x18000ce03  test    byte ptr [rcx+1Ch], 8
0x18000ce07  jz      short loc_18000CE21
0x18000ce09  mov     rcx, [rcx+10h]
0x18000ce0d  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000ce14  mov     edx, 1Dh
0x18000ce19  mov     r9d, eax
0x18000ce1c  call    WPP_SF_d
0x18000ce21  mov     eax, ebx
0x18000ce23  mov     rbx, [rsp+28h+arg_10]
0x18000ce28  add     rsp, 20h
0x18000ce2c  pop     rdi
0x18000ce2d  retn
```
