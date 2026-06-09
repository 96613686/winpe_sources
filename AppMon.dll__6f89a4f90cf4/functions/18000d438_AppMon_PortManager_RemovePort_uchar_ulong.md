# AppMon::PortManager::RemovePort(uchar *,ulong)

- ea: `0x18000d438`
- end: `0x18000d4d4`
- name: `?RemovePort@PortManager@AppMon@@SAJPEAEK@Z`
- size: `156`
- prototype: `__int64 __fastcall(unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800065a8`

## callees

- `0x180005b34`
- `0x180007a78`
- `0x18000a14c`
- `0x18000d438`

## pseudocode

```c
__int64 __fastcall AppMon::PortManager::RemovePort(unsigned __int8 *a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int8 *v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  v6 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids);
  v5[0] = &v7;
  v5[1] = &v6;
  v2 = AppMon::CaptureAndConvertExceptionToHR__lambda_2e8b3482844f5c1d23c496830c2482ed___(v5);
  v3 = v2;
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids, (unsigned int)v2);
  return v3;
}

```

## disassembly

```asm
0x18000d438  mov     [rsp+arg_10], rbx
0x18000d43d  mov     [rsp+arg_8], edx
0x18000d441  mov     [rsp+arg_0], rcx
0x18000d446  push    rdi
0x18000d447  sub     rsp, 30h
0x18000d44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d452  lea     rdi, WPP_GLOBAL_Control
0x18000d459  cmp     rcx, rdi
0x18000d45c  jz      short loc_18000D479
0x18000d45e  test    byte ptr [rcx+1Ch], 1
0x18000d462  jz      short loc_18000D479
0x18000d464  mov     rcx, [rcx+10h]
0x18000d468  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d46f  mov     edx, 0Eh
0x18000d474  call    WPP_SF_
0x18000d479  lea     rax, [rsp+38h+arg_8]
0x18000d47e  mov     [rsp+38h+var_18], rax
0x18000d483  lea     rcx, [rsp+38h+var_18]
0x18000d488  lea     rax, [rsp+38h+arg_0]
0x18000d48d  mov     [rsp+38h+var_10], rax
0x18000d492  call    AppMon__CaptureAndConvertExceptionToHR__lambda_2e8b3482844f5c1d23c496830c2482ed___
0x18000d497  mov     ebx, eax
0x18000d499  test    eax, eax
0x18000d49b  jns     short loc_18000D4C7
0x18000d49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4a4  cmp     rcx, rdi
0x18000d4a7  jz      short loc_18000D4C7
0x18000d4a9  test    byte ptr [rcx+1Ch], 8
0x18000d4ad  jz      short loc_18000D4C7
0x18000d4af  mov     rcx, [rcx+10h]
0x18000d4b3  lea     r8, WPP_9a5da8474af33cfd7c10d390b4452cc5_Traceguids
0x18000d4ba  mov     edx, 0Fh
0x18000d4bf  mov     r9d, eax
0x18000d4c2  call    WPP_SF_d
0x18000d4c7  mov     eax, ebx
0x18000d4c9  mov     rbx, [rsp+38h+arg_10]
0x18000d4ce  add     rsp, 30h
0x18000d4d2  pop     rdi
0x18000d4d3  retn
```
