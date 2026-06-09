# ShieldProvider::GetLogsDir(ushort * *)

- ea: `0x140006008`
- end: `0x140006153`
- name: `?GetLogsDir@ShieldProvider@@YAJPEAPEAG@Z`
- size: `331`
- prototype: `__int64 __fastcall(ShieldProvider *this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002f00`
- `0x14000329c`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140006008`
- `0x14000ea5c`
- `0x14000f3ac`

## string_xrefs

- `0x140006027`: `%programdata%\Microsoft\Windows Security Health`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetLogsDir(ShieldProvider *this, unsigned __int16 **a2, const unsigned __int16 *a3)
{
  int v4; // eax
  unsigned __int64 v5; // rdx
  unsigned int v6; // ebx
  _QWORD *v7; // r10
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // r8
  int v11; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // esi
  unsigned __int16 *v14; // [rsp+38h] [rbp+10h] BYREF

  v14 = 0;
  v4 = CommonUtil::UtilExpandEnvironmentStrings(
         (CommonUtil *)&v14,
         (unsigned __int16 **)L"%programdata%\\Microsoft\\Windows Security Health",
         a3);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v9 = v14;
    v10 = v14;
    v14 = 0;
    v11 = CommonUtil::NewSprintfW((CommonUtil *)&v14, (unsigned __int16 **)L"%s\\Logs", v10);
    v13 = v11;
    if ( v11 >= 0 )
    {
      *(_QWORD *)this = v14;
      if ( v9 )
        operator delete(v9, v12);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
          (unsigned int)v11);
      if ( v14 )
        operator delete(v14, v12);
      if ( v9 )
        operator delete(v9, v12);
      return v13;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
        (unsigned int)v4);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v14 )
    {
      operator delete(v14, v5);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_d(v7[2], 11, &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, v6);
    return v6;
  }
}

```

## disassembly

```asm
0x140006008  mov     rax, rsp
0x14000600b  mov     [rax+8], rbx
0x14000600f  mov     [rax+18h], rsi
0x140006013  push    rdi
0x140006014  sub     rsp, 20h
0x140006018  mov     rdi, rcx
0x14000601b  mov     qword ptr [rax+10h], 0
0x140006023  lea     rcx, [rax+10h]; this
0x140006027  lea     rdx, aProgramdataMic; "%programdata%\\Microsoft\\Windows Secur"...
0x14000602e  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::UtilExpandEnvironmentStrings(ushort * *,ushort const *)
0x140006033  mov     ebx, eax
0x140006035  test    eax, eax
0x140006037  jns     short loc_1400060B3
0x140006039  mov     r10, cs:WPP_GLOBAL_Control
0x140006040  lea     rdi, WPP_GLOBAL_Control
0x140006047  cmp     r10, rdi
0x14000604a  jz      short loc_140006072
0x14000604c  test    byte ptr [r10+1Ch], 1
0x140006051  jz      short loc_140006072
0x140006053  mov     rcx, [r10+10h]
0x140006057  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x14000605e  mov     edx, 0Ah
0x140006063  mov     r9d, eax
0x140006066  call    WPP_SF_d
0x14000606b  mov     r10, cs:WPP_GLOBAL_Control
0x140006072  mov     rcx, [rsp+28h+arg_8]; void *
0x140006077  test    rcx, rcx
0x14000607a  jz      short loc_140006088
0x14000607c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006081  mov     r10, cs:WPP_GLOBAL_Control
0x140006088  cmp     r10, rdi
0x14000608b  jz      short loc_1400060AC
0x14000608d  test    byte ptr [r10+1Ch], 1
0x140006092  jz      short loc_1400060AC
0x140006094  mov     rcx, [r10+10h]
0x140006098  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x14000609f  mov     edx, 0Bh
0x1400060a4  mov     r9d, ebx
0x1400060a7  call    WPP_SF_d
0x1400060ac  mov     eax, ebx
0x1400060ae  jmp     loc_140006143
0x1400060b3  mov     rbx, [rsp+28h+arg_8]
0x1400060b8  lea     rdx, aSLogs; "%s\\Logs"
0x1400060bf  mov     r8, rbx; unsigned __int16 *
0x1400060c2  mov     [rsp+28h+arg_8], 0
0x1400060cb  lea     rcx, [rsp+28h+arg_8]; this
0x1400060d0  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1400060d5  mov     esi, eax
0x1400060d7  test    eax, eax
0x1400060d9  jns     short loc_14000612C
0x1400060db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060e2  lea     rdi, WPP_GLOBAL_Control
0x1400060e9  cmp     rcx, rdi
0x1400060ec  jz      short loc_14000610C
0x1400060ee  test    byte ptr [rcx+1Ch], 1
0x1400060f2  jz      short loc_14000610C
0x1400060f4  mov     rcx, [rcx+10h]
0x1400060f8  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1400060ff  mov     edx, 0Ch
0x140006104  mov     r9d, eax
0x140006107  call    WPP_SF_d
0x14000610c  mov     rcx, [rsp+28h+arg_8]; void *
0x140006111  test    rcx, rcx
0x140006114  jz      short loc_14000611B
0x140006116  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000611b  test    rbx, rbx
0x14000611e  jz      short loc_140006128
0x140006120  mov     rcx, rbx; void *
0x140006123  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006128  mov     eax, esi
0x14000612a  jmp     short loc_140006143
0x14000612c  mov     rax, [rsp+28h+arg_8]
0x140006131  mov     [rdi], rax
0x140006134  test    rbx, rbx
0x140006137  jz      short loc_140006141
0x140006139  mov     rcx, rbx; void *
0x14000613c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006141  xor     eax, eax
0x140006143  mov     rbx, [rsp+28h+arg_0]
0x140006148  mov     rsi, [rsp+28h+arg_10]
0x14000614d  add     rsp, 20h
0x140006151  pop     rdi
0x140006152  retn
```
