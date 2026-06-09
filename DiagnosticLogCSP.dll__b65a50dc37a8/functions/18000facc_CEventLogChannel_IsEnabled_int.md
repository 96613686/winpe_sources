# CEventLogChannel::IsEnabled(int &)

- ea: `0x18000facc`
- end: `0x18000fc1d`
- name: `?IsEnabled@CEventLogChannel@@QEAAJAEAH@Z`
- size: `337`
- prototype: `__int64 __fastcall(CEventLogChannel *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008ff0`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x18000facc`
- `0x180011a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fbc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fbc3`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000fbe9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000fbe9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18000fbb3`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18000fbb3`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000fb60`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000fb60`

## pseudocode

```c
__int64 __fastcall CEventLogChannel::IsEnabled(CEventLogChannel *this, int *a2)
{
  signed int v4; // edi
  int v5; // eax
  EVT_HANDLE v6; // rbx
  signed int v7; // eax
  signed int LastError; // eax
  unsigned int v10; // [rsp+30h] [rbp-248h] BYREF
  DWORD PropertyValueBufferUsed; // [rsp+34h] [rbp-244h] BYREF
  struct _EVT_VARIANT PropertyValueBuffer; // [rsp+38h] [rbp-240h] BYREF
  WCHAR ChannelPath[264]; // [rsp+50h] [rbp-228h] BYREF

  PropertyValueBufferUsed = 0;
  PropertyValueBuffer = 0;
  memset_0(ChannelPath, 0, 0x20Au);
  v10 = 261;
  v4 = 0;
  v5 = ATL::CRegKey::QueryStringValue(this, &String2, ChannelPath, &v10);
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    else
      v4 = v5;
  }
  if ( v4 >= 0 )
  {
    v6 = EvtOpenChannelConfig(0, ChannelPath, 0);
    if ( v6 )
    {
      if ( EvtGetChannelConfigProperty(
             v6,
             EvtChannelConfigEnabled,
             0,
             0x10u,
             &PropertyValueBuffer,
             &PropertyValueBufferUsed) )
      {
        *a2 = PropertyValueBuffer.BooleanVal;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      EvtClose(v6);
    }
    else
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000facc  mov     [rsp+arg_10], rbx
0x18000fad1  mov     [rsp+arg_18], rsi
0x18000fad6  push    rdi
0x18000fad7  sub     rsp, 270h
0x18000fade  mov     rax, cs:__security_cookie
0x18000fae5  xor     rax, rsp
0x18000fae8  mov     [rsp+278h+var_18], rax
0x18000faf0  mov     rsi, rdx
0x18000faf3  mov     [rsp+278h+var_244], 0
0x18000fafb  mov     rbx, rcx
0x18000fafe  xorps   xmm0, xmm0
0x18000fb01  xor     edx, edx; Val
0x18000fb03  lea     rcx, [rsp+278h+ChannelPath]; void *
0x18000fb08  mov     r8d, 20Ah; Size
0x18000fb0e  movups  xmmword ptr [rsp+278h+var_240], xmm0
0x18000fb13  call    memset_0
0x18000fb18  lea     r9, [rsp+278h+var_248]; unsigned int *
0x18000fb1d  mov     [rsp+278h+var_248], 105h
0x18000fb25  lea     r8, [rsp+278h+ChannelPath]; unsigned __int16 *
0x18000fb2a  mov     rcx, rbx; this
0x18000fb2d  lea     rdx, String2; unsigned __int16 *
0x18000fb34  xor     edi, edi
0x18000fb36  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000fb3b  test    eax, eax
0x18000fb3d  jz      short loc_18000FB4E
0x18000fb3f  jg      short loc_18000FB45
0x18000fb41  mov     edi, eax
0x18000fb43  jmp     short loc_18000FB4E
0x18000fb45  movzx   edi, ax
0x18000fb48  or      edi, 80070000h
0x18000fb4e  test    edi, edi
0x18000fb50  js      loc_18000FBF5
0x18000fb56  xor     r8d, r8d; Flags
0x18000fb59  lea     rdx, [rsp+278h+ChannelPath]; ChannelPath
0x18000fb5e  xor     ecx, ecx; Session
0x18000fb60  call    cs:__imp_EvtOpenChannelConfig
0x18000fb67  nop     dword ptr [rax+rax+00h]
0x18000fb6c  mov     rbx, rax
0x18000fb6f  test    rax, rax
0x18000fb72  jnz     short loc_18000FB91
0x18000fb74  call    cs:__imp_GetLastError
0x18000fb7b  nop     dword ptr [rax+rax+00h]
0x18000fb80  mov     edi, eax
0x18000fb82  test    eax, eax
0x18000fb84  jle     short loc_18000FBF5
0x18000fb86  movzx   edi, ax
0x18000fb89  or      edi, 80070000h
0x18000fb8f  jmp     short loc_18000FBF5
0x18000fb91  lea     rax, [rsp+278h+var_244]
0x18000fb96  mov     r9d, 10h; PropertyValueBufferSize
0x18000fb9c  mov     [rsp+278h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x18000fba1  xor     r8d, r8d; Flags
0x18000fba4  lea     rax, [rsp+278h+var_240]
0x18000fba9  xor     edx, edx; PropertyId
0x18000fbab  mov     rcx, rbx; ChannelConfig
0x18000fbae  mov     [rsp+278h+PropertyValueBuffer], rax; PropertyValueBuffer
0x18000fbb3  call    cs:__imp_EvtGetChannelConfigProperty
0x18000fbba  nop     dword ptr [rax+rax+00h]
0x18000fbbf  test    eax, eax
0x18000fbc1  jnz     short loc_18000FBE0
0x18000fbc3  call    cs:__imp_GetLastError
0x18000fbca  nop     dword ptr [rax+rax+00h]
0x18000fbcf  mov     edi, eax
0x18000fbd1  test    eax, eax
0x18000fbd3  jle     short loc_18000FBE6
0x18000fbd5  movzx   edi, ax
0x18000fbd8  or      edi, 80070000h
0x18000fbde  jmp     short loc_18000FBE6
0x18000fbe0  mov     ecx, dword ptr [rsp+278h+var_240]
0x18000fbe4  mov     [rsi], ecx
0x18000fbe6  mov     rcx, rbx; Object
0x18000fbe9  call    cs:__imp_EvtClose
0x18000fbf0  nop     dword ptr [rax+rax+00h]
0x18000fbf5  mov     eax, edi
0x18000fbf7  mov     rcx, [rsp+278h+var_18]
0x18000fbff  xor     rcx, rsp; StackCookie
0x18000fc02  call    __security_check_cookie
0x18000fc07  lea     r11, [rsp+278h+var_8]
0x18000fc0f  mov     rbx, [r11+20h]
0x18000fc13  mov     rsi, [r11+28h]
0x18000fc17  mov     rsp, r11
0x18000fc1a  pop     rdi
0x18000fc1b  retn
```
