# AppMon::PortManager::CreateAppPortEntry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<AppMon::AppPortEntry> &)

- ea: `0x18000cc5c`
- end: `0x18000ccf5`
- name: `?CreateAppPortEntry@PortManager@AppMon@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@VAppPortEntry@AppMon@@@4@@Z`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000681c`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a17c`
- `0x18000cc5c`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::CreateAppPortEntry(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v7[0] = a1;
  v7[1] = a2;
  v4 = AppMon::CaptureAndConvertExceptionToHR__lambda_558c0dbe5407213702eb25640467f752___(v7);
  v5 = v4;
  if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v4);
  return v5;
}

```

## disassembly

```asm
0x18000cc5c  mov     [rsp+arg_0], rbx
0x18000cc61  mov     [rsp+arg_8], rsi
0x18000cc66  push    rdi
0x18000cc67  sub     rsp, 30h
0x18000cc6b  mov     rbx, rdx
0x18000cc6e  mov     rdi, rcx
0x18000cc71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc78  lea     rsi, WPP_GLOBAL_Control
0x18000cc7f  cmp     rcx, rsi
0x18000cc82  jz      short loc_18000CC9F
0x18000cc84  test    byte ptr [rcx+1Ch], 1
0x18000cc88  jz      short loc_18000CC9F
0x18000cc8a  mov     rcx, [rcx+10h]
0x18000cc8e  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000cc95  mov     edx, 1Ah
0x18000cc9a  call    WPP_SF_
0x18000cc9f  lea     rcx, [rsp+38h+var_18]
0x18000cca4  mov     [rsp+38h+var_18], rdi
0x18000cca9  mov     [rsp+38h+var_10], rbx
0x18000ccae  call    AppMon__CaptureAndConvertExceptionToHR__lambda_558c0dbe5407213702eb25640467f752___
0x18000ccb3  mov     ebx, eax
0x18000ccb5  test    eax, eax
0x18000ccb7  jns     short loc_18000CCE3
0x18000ccb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc0  cmp     rcx, rsi
0x18000ccc3  jz      short loc_18000CCE3
0x18000ccc5  test    byte ptr [rcx+1Ch], 8
0x18000ccc9  jz      short loc_18000CCE3
0x18000cccb  mov     rcx, [rcx+10h]
0x18000cccf  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000ccd6  mov     edx, 1Bh
0x18000ccdb  mov     r9d, eax
0x18000ccde  call    WPP_SF_d
0x18000cce3  mov     rsi, [rsp+38h+arg_8]
0x18000cce8  mov     eax, ebx
0x18000ccea  mov     rbx, [rsp+38h+arg_0]
0x18000ccef  add     rsp, 30h
0x18000ccf3  pop     rdi
0x18000ccf4  retn
```
