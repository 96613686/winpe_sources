# JobHelper::DeleteWmiApp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000cb4c`
- end: `0x18000ccac`
- name: `?DeleteWmiApp@JobHelper@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006df0`

## callees

- `0x18000702c`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000b8b4`
- `0x18000bd00`
- `0x18000c354`
- `0x18000c734`
- `0x18000cb4c`
- `0x18000ea88`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobHelper::DeleteWmiApp(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  int Job; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  int v8; // eax
  JobHelper *v9; // rcx
  int v10; // eax
  _BYTE v12[40]; // [rsp+38h] [rbp-180h] BYREF
  _BYTE v13[320]; // [rsp+60h] [rbp-158h] BYREF

  _SwJob::_SwJob((_SwJob *)v13);
  v4 = (_QWORD *)std::wstring::wstring(v12, a2);
  Job = JobHelper::GetJob(a1, v4, (__int64)v13);
  v6 = Job;
  if ( Job >= 0 )
  {
    v7 = (_QWORD *)std::wstring::wstring(v12, v13);
    v8 = JobHelper::DeleteJob(a1, v7);
    if ( v8 < 0 )
    {
      v9 = (JobHelper *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          212,
          &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)v8);
    }
    v10 = JobHelper::DeleteApp(v9, (struct _SwJob *)v13);
    v6 = v10;
    if ( v10 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        213,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)v10);
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    if ( a2[3] >= 8u )
      a2 = (_QWORD *)*a2;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      211,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)a2,
      Job);
  }
  _SwJob::~_SwJob((_SwJob *)v13);
  return v6;
}

```

## disassembly

```asm
0x18000cb4c  mov     [rsp+arg_10], rbx
0x18000cb51  mov     [rsp+arg_18], rsi
0x18000cb56  push    rdi
0x18000cb57  sub     rsp, 1B0h
0x18000cb5e  mov     rax, cs:__security_cookie
0x18000cb65  xor     rax, rsp
0x18000cb68  mov     [rsp+1B8h+var_18], rax
0x18000cb70  mov     rdi, rdx
0x18000cb73  mov     rsi, rcx
0x18000cb76  lea     rcx, [rsp+1B8h+var_158]; this
0x18000cb7b  call    ??0_SwJob@@QEAA@XZ; _SwJob::_SwJob(void)
0x18000cb80  nop
0x18000cb81  mov     rdx, rdi
0x18000cb84  lea     rcx, [rsp+1B8h+var_180]
0x18000cb89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cb8e  lea     r8, [rsp+1B8h+var_158]
0x18000cb93  mov     rdx, rax
0x18000cb96  mov     rcx, rsi
0x18000cb99  call    ?GetJob@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SwJob@@@Z; JobHelper::GetJob(std::wstring,_SwJob &)
0x18000cb9e  mov     ebx, eax
0x18000cba0  test    eax, eax
0x18000cba2  jns     short loc_18000CBF0
0x18000cba4  lea     rsi, WPP_GLOBAL_Control
0x18000cbab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbb2  cmp     rcx, rsi
0x18000cbb5  jz      loc_18000CC7A
0x18000cbbb  test    byte ptr [rcx+1Ch], 4
0x18000cbbf  jz      loc_18000CC7A
0x18000cbc5  cmp     qword ptr [rdi+18h], 8
0x18000cbca  jb      short loc_18000CBCF
0x18000cbcc  mov     rdi, [rdi]
0x18000cbcf  mov     edx, 0D3h
0x18000cbd4  mov     [rsp+1B8h+var_198], eax
0x18000cbd8  mov     r9, rdi
0x18000cbdb  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000cbe2  mov     rcx, [rcx+10h]
0x18000cbe6  call    WPP_SF_Sd
0x18000cbeb  jmp     loc_18000CC7A
0x18000cbf0  lea     rdx, [rsp+1B8h+var_158]
0x18000cbf5  lea     rcx, [rsp+1B8h+var_180]
0x18000cbfa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cbff  mov     rdx, rax
0x18000cc02  mov     rcx, rsi
0x18000cc05  call    ?DeleteJob@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JobHelper::DeleteJob(std::wstring)
0x18000cc0a  lea     rsi, WPP_GLOBAL_Control
0x18000cc11  test    eax, eax
0x18000cc13  jns     short loc_18000CC3F
0x18000cc15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc1c  cmp     rcx, rsi
0x18000cc1f  jz      short loc_18000CC3F
0x18000cc21  test    byte ptr [rcx+1Ch], 4
0x18000cc25  jz      short loc_18000CC3F
0x18000cc27  mov     edx, 0D4h
0x18000cc2c  mov     r9d, eax
0x18000cc2f  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000cc36  mov     rcx, [rcx+10h]
0x18000cc3a  call    WPP_SF_d
0x18000cc3f  lea     rdx, [rsp+1B8h+var_158]; struct _SwJob *
0x18000cc44  call    ?DeleteApp@JobHelper@@AEAAJAEAU_SwJob@@@Z; JobHelper::DeleteApp(_SwJob &)
0x18000cc49  mov     ebx, eax
0x18000cc4b  test    eax, eax
0x18000cc4d  jns     short loc_18000CC7A
0x18000cc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc56  cmp     rcx, rsi
0x18000cc59  jz      short loc_18000CC7A
0x18000cc5b  test    byte ptr [rcx+1Ch], 4
0x18000cc5f  jz      short loc_18000CC7A
0x18000cc61  mov     edx, 0D5h
0x18000cc66  mov     r9d, eax
0x18000cc69  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000cc70  mov     rcx, [rcx+10h]
0x18000cc74  call    WPP_SF_d
0x18000cc79  nop
0x18000cc7a  lea     rcx, [rsp+1B8h+var_158]; this
0x18000cc7f  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18000cc84  mov     eax, ebx
0x18000cc86  mov     rcx, [rsp+1B8h+var_18]
0x18000cc8e  xor     rcx, rsp; StackCookie
0x18000cc91  call    __security_check_cookie
0x18000cc96  lea     r11, [rsp+1B8h+var_8]
0x18000cc9e  mov     rbx, [r11+20h]
0x18000cca2  mov     rsi, [r11+28h]
0x18000cca6  mov     rsp, r11
0x18000cca9  pop     rdi
0x18000ccaa  retn
```
