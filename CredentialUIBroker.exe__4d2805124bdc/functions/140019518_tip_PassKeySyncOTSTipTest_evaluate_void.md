# _tip_PassKeySyncOTSTipTest::evaluate(void)

- ea: `0x140019518`
- end: `0x140019648`
- name: `?evaluate@_tip_PassKeySyncOTSTipTest@@QEAAXXZ`
- size: `304`
- prototype: `void __fastcall(_tip_PassKeySyncOTSTipTest *this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140019490`

## callees

- `0x140019518`
- `0x14001aa9c`

## string_xrefs

- `0x140019528`: `reason::ControllerInstanceNotCreated`
- `0x140019567`: `reason::PasskeySyncOTSThroughBrokerFailed`

## pseudocode

```c
void __fastcall _tip_PassKeySyncOTSTipTest::evaluate(_tip_PassKeySyncOTSTipTest *this, const char *a2)
{
  const char *v2; // rax
  __int64 v3; // r8
  __int64 v4; // rdx
  char v5; // r9
  __int64 v6; // r8
  char v7; // r9
  __int64 v8; // r8
  char v9; // r9
  __int64 v10; // r8
  const char *v11; // rax
  __int64 v12; // r8
  char v13; // r9

  if ( *((int *)this + 4) < 0 )
  {
    v2 = tip2::details::reason_string((tip2::details *)"reason::ControllerInstanceNotCreated", a2);
    v4 = *(_QWORD *)(v3 + 8);
    if ( *(_BYTE *)(v4 + 152) != v5 )
      return;
    *(_WORD *)(v4 + 154) = 2;
    goto LABEL_4;
  }
  if ( *((int *)this + 5) >= 0 )
  {
    if ( *((int *)this + 6) >= 0 )
    {
      v10 = *((_QWORD *)this + 1);
      if ( (*(_DWORD *)(v10 + 56) & 0x200) != 0 )
      {
        if ( !*(_QWORD *)(v10 + 80) )
        {
          v11 = tip2::details::reason_string((tip2::details *)"reason::Succeeded", a2);
          if ( *(_BYTE *)(v12 + 152) == v13 )
          {
            *(_QWORD *)(v12 + 160) = v11;
            *(_BYTE *)(v12 + 152) = 1;
            *(_WORD *)(v12 + 154) = 1;
          }
          return;
        }
        if ( *(_BYTE *)(v10 + 152) )
          return;
        *(_WORD *)(v10 + 154) = 0x4000;
      }
      else
      {
        if ( *(_BYTE *)(v10 + 152) )
          return;
        *(_WORD *)(v10 + 154) = 16385;
      }
      *(_BYTE *)(v10 + 152) = 3;
      *(_QWORD *)(v10 + 160) = 0;
      return;
    }
    v2 = tip2::details::reason_string((tip2::details *)"reason::ShellHostLaunchFailed", a2);
    v4 = *(_QWORD *)(v8 + 8);
    if ( *(_BYTE *)(v4 + 152) == v9 )
    {
      *(_WORD *)(v4 + 154) = 4;
LABEL_4:
      *(_BYTE *)(v4 + 152) = 3;
LABEL_5:
      *(_QWORD *)(v4 + 160) = v2;
    }
  }
  else
  {
    v2 = tip2::details::reason_string((tip2::details *)"reason::PasskeySyncOTSThroughBrokerFailed", a2);
    v4 = *(_QWORD *)(v6 + 8);
    if ( *(_BYTE *)(v4 + 152) == v7 )
    {
      *(_BYTE *)(v4 + 152) = 3;
      *(_WORD *)(v4 + 154) = 3;
      goto LABEL_5;
    }
  }
}

```

## disassembly

```asm
0x140019518  sub     rsp, 28h
0x14001951c  xor     r9d, r9d
0x14001951f  mov     r8, rcx
0x140019522  cmp     [rcx+10h], r9d
0x140019526  jge     short loc_140019561
0x140019528  lea     rcx, aReasonControll; "reason::ControllerInstanceNotCreated"
0x14001952f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140019534  mov     rdx, [r8+8]; char *
0x140019538  cmp     [rdx+98h], r9b
0x14001953f  jnz     loc_140019643
0x140019545  mov     word ptr [rdx+9Ah], 2
0x14001954e  mov     byte ptr [rdx+98h], 3
0x140019555  mov     [rdx+0A0h], rax
0x14001955c  jmp     loc_140019643
0x140019561  cmp     [rcx+14h], r9d
0x140019565  jge     short loc_140019598
0x140019567  lea     rcx, aReasonPasskeys; "reason::PasskeySyncOTSThroughBrokerFail"...
0x14001956e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x140019573  mov     rdx, [r8+8]; char *
0x140019577  cmp     [rdx+98h], r9b
0x14001957e  jnz     loc_140019643
0x140019584  mov     ecx, 3
0x140019589  mov     [rdx+98h], cl
0x14001958f  mov     [rdx+9Ah], cx
0x140019596  jmp     short loc_140019555
0x140019598  cmp     [rcx+18h], r9d
0x14001959c  jge     short loc_1400195C6
0x14001959e  lea     rcx, aReasonShellhos; "reason::ShellHostLaunchFailed"
0x1400195a5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1400195aa  mov     rdx, [r8+8]; char *
0x1400195ae  cmp     [rdx+98h], r9b
0x1400195b5  jnz     loc_140019643
0x1400195bb  mov     word ptr [rdx+9Ah], 4
0x1400195c4  jmp     short loc_14001954E
0x1400195c6  mov     r8, [rcx+8]
0x1400195ca  test    dword ptr [r8+38h], 200h
0x1400195d2  jnz     short loc_1400195F8
0x1400195d4  cmp     [r8+98h], r9b
0x1400195db  jnz     short loc_140019643
0x1400195dd  mov     word ptr [r8+9Ah], 4001h
0x1400195e7  mov     byte ptr [r8+98h], 3
0x1400195ef  mov     [r8+0A0h], r9
0x1400195f6  jmp     short loc_140019643
0x1400195f8  cmp     [r8+50h], r9
0x1400195fc  jz      short loc_140019613
0x1400195fe  cmp     [r8+98h], r9b
0x140019605  jnz     short loc_140019643
0x140019607  mov     word ptr [r8+9Ah], 4000h
0x140019611  jmp     short loc_1400195E7
0x140019613  lea     rcx, aReasonSucceede; "reason::Succeeded"
0x14001961a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14001961f  cmp     [r8+98h], r9b
0x140019626  jnz     short loc_140019643
0x140019628  mov     ecx, 1
0x14001962d  mov     [r8+0A0h], rax
0x140019634  mov     [r8+98h], cl
0x14001963b  mov     [r8+9Ah], cx
0x140019643  add     rsp, 28h
0x140019647  retn
```
