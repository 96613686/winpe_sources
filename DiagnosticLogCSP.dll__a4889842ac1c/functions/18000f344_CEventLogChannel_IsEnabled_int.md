# CEventLogChannel::IsEnabled(int &)

- ea: `0x18000f344`
- end: `0x18000f476`
- name: `?IsEnabled@CEventLogChannel@@QEAAJAEAH@Z`
- size: `306`
- prototype: `__int64 __fastcall(CEventLogChannel *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008dc0`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x18000f344`
- `0x180011170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f429`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f449`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18000f449`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18000f41f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18000f41f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f3d8`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18000f3d8`

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
0x18000f344  mov     [rsp+arg_10], rbx
0x18000f349  mov     [rsp+arg_18], rsi
0x18000f34e  push    rdi
0x18000f34f  sub     rsp, 270h
0x18000f356  mov     rax, cs:__security_cookie
0x18000f35d  xor     rax, rsp
0x18000f360  mov     [rsp+278h+var_18], rax
0x18000f368  mov     rsi, rdx
0x18000f36b  mov     [rsp+278h+var_244], 0
0x18000f373  mov     rbx, rcx
0x18000f376  xorps   xmm0, xmm0
0x18000f379  xor     edx, edx; Val
0x18000f37b  lea     rcx, [rsp+278h+ChannelPath]; void *
0x18000f380  mov     r8d, 20Ah; Size
0x18000f386  movups  xmmword ptr [rsp+278h+var_240], xmm0
0x18000f38b  call    memset_0
0x18000f390  lea     r9, [rsp+278h+var_248]; unsigned int *
0x18000f395  mov     [rsp+278h+var_248], 105h
0x18000f39d  lea     r8, [rsp+278h+ChannelPath]; unsigned __int16 *
0x18000f3a2  mov     rcx, rbx; this
0x18000f3a5  lea     rdx, String2; unsigned __int16 *
0x18000f3ac  xor     edi, edi
0x18000f3ae  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000f3b3  test    eax, eax
0x18000f3b5  jz      short loc_18000F3C6
0x18000f3b7  jg      short loc_18000F3BD
0x18000f3b9  mov     edi, eax
0x18000f3bb  jmp     short loc_18000F3C6
0x18000f3bd  movzx   edi, ax
0x18000f3c0  or      edi, 80070000h
0x18000f3c6  test    edi, edi
0x18000f3c8  js      loc_18000F44F
0x18000f3ce  xor     r8d, r8d; Flags
0x18000f3d1  lea     rdx, [rsp+278h+ChannelPath]; ChannelPath
0x18000f3d6  xor     ecx, ecx; Session
0x18000f3d8  call    cs:__imp_EvtOpenChannelConfig
0x18000f3de  mov     rbx, rax
0x18000f3e1  test    rax, rax
0x18000f3e4  jnz     short loc_18000F3FD
0x18000f3e6  call    cs:__imp_GetLastError
0x18000f3ec  mov     edi, eax
0x18000f3ee  test    eax, eax
0x18000f3f0  jle     short loc_18000F44F
0x18000f3f2  movzx   edi, ax
0x18000f3f5  or      edi, 80070000h
0x18000f3fb  jmp     short loc_18000F44F
0x18000f3fd  lea     rax, [rsp+278h+var_244]
0x18000f402  mov     r9d, 10h; PropertyValueBufferSize
0x18000f408  mov     [rsp+278h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x18000f40d  xor     r8d, r8d; Flags
0x18000f410  lea     rax, [rsp+278h+var_240]
0x18000f415  xor     edx, edx; PropertyId
0x18000f417  mov     rcx, rbx; ChannelConfig
0x18000f41a  mov     [rsp+278h+PropertyValueBuffer], rax; PropertyValueBuffer
0x18000f41f  call    cs:__imp_EvtGetChannelConfigProperty
0x18000f425  test    eax, eax
0x18000f427  jnz     short loc_18000F440
0x18000f429  call    cs:__imp_GetLastError
0x18000f42f  mov     edi, eax
0x18000f431  test    eax, eax
0x18000f433  jle     short loc_18000F446
0x18000f435  movzx   edi, ax
0x18000f438  or      edi, 80070000h
0x18000f43e  jmp     short loc_18000F446
0x18000f440  mov     ecx, dword ptr [rsp+278h+var_240]
0x18000f444  mov     [rsi], ecx
0x18000f446  mov     rcx, rbx; Object
0x18000f449  call    cs:__imp_EvtClose
0x18000f44f  mov     eax, edi
0x18000f451  mov     rcx, [rsp+278h+var_18]
0x18000f459  xor     rcx, rsp; StackCookie
0x18000f45c  call    __security_check_cookie
0x18000f461  lea     r11, [rsp+278h+var_8]
0x18000f469  mov     rbx, [r11+20h]
0x18000f46d  mov     rsi, [r11+28h]
0x18000f471  mov     rsp, r11
0x18000f474  pop     rdi
0x18000f475  retn
```
