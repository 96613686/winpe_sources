# AppMon::PortManager::LoadAppPrinterEndPointFromRegistry(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>> &)

- ea: `0x18000d24c`
- end: `0x18000d2d8`
- name: `?LoadAppPrinterEndPointFromRegistry@PortManager@AppMon@@CAJAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@@std@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c0cc`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a1ac`
- `0x18000b04c`
- `0x18000d24c`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::LoadAppPrinterEndPointFromRegistry(__int64 a1)
{
  __int64 v1; // rax
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v1 = lambda_5cb43ad01037aa628a1cc5978b1aaf7b_::_lambda_5cb43ad01037aa628a1cc5978b1aaf7b_(&v5);
  v2 = AppMon::CaptureAndConvertExceptionToHR__lambda_5cb43ad01037aa628a1cc5978b1aaf7b___(v1);
  v3 = v2;
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x18000d24c  mov     [rsp+arg_8], rbx
0x18000d251  mov     [rsp+arg_0], rcx
0x18000d256  push    rdi
0x18000d257  sub     rsp, 20h
0x18000d25b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d262  lea     rdi, WPP_GLOBAL_Control
0x18000d269  cmp     rcx, rdi
0x18000d26c  jz      short loc_18000D289
0x18000d26e  test    byte ptr [rcx+1Ch], 1
0x18000d272  jz      short loc_18000D289
0x18000d274  mov     rcx, [rcx+10h]
0x18000d278  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d27f  mov     edx, 14h
0x18000d284  call    WPP_SF_
0x18000d289  lea     rcx, [rsp+28h+arg_0]
0x18000d28e  call    _lambda_5cb43ad01037aa628a1cc5978b1aaf7b____lambda_5cb43ad01037aa628a1cc5978b1aaf7b_
0x18000d293  mov     rcx, rax
0x18000d296  call    AppMon__CaptureAndConvertExceptionToHR__lambda_5cb43ad01037aa628a1cc5978b1aaf7b___
0x18000d29b  mov     ebx, eax
0x18000d29d  test    eax, eax
0x18000d29f  jns     short loc_18000D2CB
0x18000d2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a8  cmp     rcx, rdi
0x18000d2ab  jz      short loc_18000D2CB
0x18000d2ad  test    byte ptr [rcx+1Ch], 8
0x18000d2b1  jz      short loc_18000D2CB
0x18000d2b3  mov     rcx, [rcx+10h]
0x18000d2b7  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d2be  mov     edx, 15h
0x18000d2c3  mov     r9d, eax
0x18000d2c6  call    WPP_SF_d
0x18000d2cb  mov     eax, ebx
0x18000d2cd  mov     rbx, [rsp+28h+arg_8]
0x18000d2d2  add     rsp, 20h
0x18000d2d6  pop     rdi
0x18000d2d7  retn
```
