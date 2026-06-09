# WiFiTaskPipeClient::Start(WiFiTaskServer)

- ea: `0x14000a4a0`
- end: `0x14000a622`
- name: `?Start@WiFiTaskPipeClient@@QEAAJW4WiFiTaskServer@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000728c`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x140006064`
- `0x140009994`
- `0x14000a4a0`
- `0x14000a6b4`
- `0x14000bf20`
- `0x14000c098`
- `0x14000d490`

## string_xrefs

- `0x14000a51e`: `\\.\Pipe\NlaSvcTask`
- `0x14000a515`: `\\.\Pipe\WwanSvcTask`
- `0x14000a527`: `\\.\Pipe\WiFiNetworkManagerTask`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::Start(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  const WCHAR *v4; // rbx
  WiFiTaskPipeClient *v5; // rsi
  int v6; // eax
  int CurrentSid; // eax
  unsigned __int8 pDestinationSid[80]; // [rsp+30h] [rbp-68h] BYREF

  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 == 1 )
    {
      v4 = L"\\\\.\\Pipe\\NlaSvcTask";
    }
    else
    {
      if ( (_DWORD)a2 != 2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            &WPP_b0092361ee8d34528df1964c4db39788_Traceguids,
            (unsigned int)a2);
        }
        return (unsigned int)-2147024809;
      }
      v4 = L"\\\\.\\Pipe\\WwanSvcTask";
    }
  }
  else
  {
    v4 = L"\\\\.\\Pipe\\WiFiNetworkManagerTask";
  }
  v5 = g_TaskPipe;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, v4);
  }
  v6 = AsyncPipe::Connect(*((AsyncPipe **)v5 + 2), v4, v5);
  v3 = v6;
  if ( v6 >= 0 )
  {
    memset_0(pDestinationSid, 0, 0x44u);
    CurrentSid = GetCurrentSid(pDestinationSid);
    if ( CurrentSid )
    {
      if ( CurrentSid > 0 )
        v3 = (unsigned __int16)CurrentSid | 0x80070000;
      else
        v3 = CurrentSid;
      WiFiTaskPipeClient::Stop(v5);
    }
    else
    {
      WiFiTaskPipeClient::SendOperationPacket(v5, 0, 0xFF00FF00, pDestinationSid, 0x44u);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_b0092361ee8d34528df1964c4db39788_Traceguids,
      (unsigned int)v6);
  }
  return v3;
}

```

## disassembly

```asm
0x14000a4a0  mov     [rsp+arg_0], rbx
0x14000a4a5  mov     [rsp+arg_10], rsi
0x14000a4aa  push    rdi
0x14000a4ab  sub     rsp, 90h
0x14000a4b2  mov     rax, cs:__security_cookie
0x14000a4b9  xor     rax, rsp
0x14000a4bc  mov     [rsp+98h+var_18], rax
0x14000a4c4  mov     r9d, edx
0x14000a4c7  mov     ecx, edx
0x14000a4c9  test    edx, edx
0x14000a4cb  jz      short loc_14000A527
0x14000a4cd  sub     ecx, 1
0x14000a4d0  jz      short loc_14000A51E
0x14000a4d2  cmp     ecx, 1
0x14000a4d5  jz      short loc_14000A515
0x14000a4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4de  lea     rdi, WPP_GLOBAL_Control
0x14000a4e5  cmp     rcx, rdi
0x14000a4e8  jz      short loc_14000A50B
0x14000a4ea  cmp     byte ptr [rcx+19h], 2
0x14000a4ee  jb      short loc_14000A50B
0x14000a4f0  test    byte ptr [rcx+1Ch], 1
0x14000a4f4  jz      short loc_14000A50B
0x14000a4f6  mov     rcx, [rcx+10h]
0x14000a4fa  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x14000a501  mov     edx, 1Ah
0x14000a506  call    WPP_SF_d
0x14000a50b  mov     ebx, 80070057h
0x14000a510  jmp     loc_14000A5FB
0x14000a515  lea     rbx, FileName; "\\\\.\\Pipe\\WwanSvcTask"
0x14000a51c  jmp     short loc_14000A52E
0x14000a51e  lea     rbx, aPipeNlasvctask; "\\\\.\\Pipe\\NlaSvcTask"
0x14000a525  jmp     short loc_14000A52E
0x14000a527  lea     rbx, aPipeWifinetwor; "\\\\.\\Pipe\\WiFiNetworkManagerTask"
0x14000a52e  mov     rsi, cs:?g_TaskPipe@@3PEAVWiFiTaskPipeClient@@EA; WiFiTaskPipeClient * g_TaskPipe
0x14000a535  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a53c  lea     rdi, WPP_GLOBAL_Control
0x14000a543  cmp     rcx, rdi
0x14000a546  jz      short loc_14000A560
0x14000a548  cmp     byte ptr [rcx+19h], 5
0x14000a54c  jb      short loc_14000A560
0x14000a54e  test    byte ptr [rcx+1Ch], 1
0x14000a552  jz      short loc_14000A560
0x14000a554  mov     rcx, [rcx+10h]
0x14000a558  mov     r9, rbx
0x14000a55b  call    WPP_SF_S
0x14000a560  mov     rcx, [rsi+10h]; this
0x14000a564  mov     r8, rsi; struct IAsyncPipeCallback *
0x14000a567  mov     rdx, rbx; lpFileName
0x14000a56a  call    ?Connect@AsyncPipe@@QEAAJPEBGPEAUIAsyncPipeCallback@@@Z; AsyncPipe::Connect(ushort const *,IAsyncPipeCallback *)
0x14000a56f  mov     ebx, eax
0x14000a571  test    eax, eax
0x14000a573  jns     short loc_14000A5A7
0x14000a575  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a57c  cmp     rcx, rdi
0x14000a57f  jz      short loc_14000A5FB
0x14000a581  cmp     byte ptr [rcx+19h], 2
0x14000a585  jb      short loc_14000A5FB
0x14000a587  test    byte ptr [rcx+1Ch], 1
0x14000a58b  jz      short loc_14000A5FB
0x14000a58d  mov     rcx, [rcx+10h]
0x14000a591  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x14000a598  mov     edx, 18h
0x14000a59d  mov     r9d, eax
0x14000a5a0  call    WPP_SF_d
0x14000a5a5  jmp     short loc_14000A5FB
0x14000a5a7  mov     edi, 44h ; 'D'
0x14000a5ac  lea     rcx, [rsp+98h+pDestinationSid]; void *
0x14000a5b1  mov     r8d, edi; Size
0x14000a5b4  xor     edx, edx; Val
0x14000a5b6  call    memset_0
0x14000a5bb  lea     rcx, [rsp+98h+pDestinationSid]; pDestinationSid
0x14000a5c0  call    ?GetCurrentSid@@YAKAEAT_SE_SID@@@Z; GetCurrentSid(_SE_SID &)
0x14000a5c5  test    eax, eax
0x14000a5c7  jz      short loc_14000A5E2
0x14000a5c9  jg      short loc_14000A5CF
0x14000a5cb  mov     ebx, eax
0x14000a5cd  jmp     short loc_14000A5D8
0x14000a5cf  movzx   ebx, ax
0x14000a5d2  or      ebx, 80070000h
0x14000a5d8  mov     rcx, rsi; this
0x14000a5db  call    ?Stop@WiFiTaskPipeClient@@QEAAJXZ; WiFiTaskPipeClient::Stop(void)
0x14000a5e0  jmp     short loc_14000A5FB
0x14000a5e2  lea     r9, [rsp+98h+pDestinationSid]; unsigned __int8 *
0x14000a5e7  mov     [rsp+98h+var_78], edi; unsigned int
0x14000a5eb  xor     edx, edx; unsigned __int64
0x14000a5ed  mov     r8d, 0FF00FF00h; unsigned int
0x14000a5f3  mov     rcx, rsi; this
0x14000a5f6  call    ?SendOperationPacket@WiFiTaskPipeClient@@QEAAJ_KKPEBEK@Z; WiFiTaskPipeClient::SendOperationPacket(unsigned __int64,ulong,uchar const *,ulong)
0x14000a5fb  mov     eax, ebx
0x14000a5fd  mov     rcx, [rsp+98h+var_18]
0x14000a605  xor     rcx, rsp; StackCookie
0x14000a608  call    __security_check_cookie
0x14000a60d  lea     r11, [rsp+98h+var_8]
0x14000a615  mov     rbx, [r11+10h]
0x14000a619  mov     rsi, [r11+20h]
0x14000a61d  mov     rsp, r11
0x14000a620  pop     rdi
0x14000a621  retn
```
