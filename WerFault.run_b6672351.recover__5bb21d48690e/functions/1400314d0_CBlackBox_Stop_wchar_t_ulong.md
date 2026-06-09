# CBlackBox::Stop(wchar_t *,ulong)

- ea: `0x1400314d0`
- end: `0x14003168d`
- name: `?Stop@CBlackBox@@SAJPEA_WK@Z`
- size: `445`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000ddb8`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140014f14`
- `0x1400314d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400315bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003162f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400315bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003162f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003160d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003160d`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x1400315a4`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x1400315a4`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x140031580`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x140031580`

## pseudocode

```c
__int64 __fastcall CBlackBox::Stop(wchar_t *a1)
{
  signed int LastError; // eax
  signed int v2; // eax
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v5[520]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR FileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(&Properties, 0, sizeof(Properties));
  memset_0(v5, 0, sizeof(v5));
  memset_0(FileName, 0, 0x208u);
  Properties.Wnode.BufferSize = 1160;
  Properties.Wnode.ClientContext = 1;
  Properties.Wnode.Flags = 0x20000;
  Properties.Wnode.Guid = (GUID)xmmword_14006A7A8;
  Properties.MaximumFileSize = 2;
  Properties.LogFileMode = 16910338;
  Properties.LoggerNameOffset = 120;
  Properties.LogFileNameOffset = 640;
  if ( !QueryTraceW(0, L"WER Tracing Session", &Properties) )
  {
    if ( StopTraceW(0, L"WER Tracing Session", &Properties) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_495391dabb8f3fb26262efb7112a6047_Traceguids,
          (unsigned int)LastError);
      }
    }
    if ( FileName[0]
      && !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = GetLastError();
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_495391dabb8f3fb26262efb7112a6047_Traceguids,
        (unsigned int)v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400314d0  mov     [rsp-8+arg_0], rbx
0x1400314d5  mov     [rsp-8+arg_8], rdi
0x1400314da  push    rbp
0x1400314db  lea     rbp, [rsp-3C0h]
0x1400314e3  sub     rsp, 4C0h
0x1400314ea  mov     rax, cs:__security_cookie
0x1400314f1  xor     rax, rsp
0x1400314f4  mov     [rbp+3C0h+var_10], rax
0x1400314fb  mov     edi, 78h ; 'x'
0x140031500  lea     rcx, [rsp+4C0h+Properties]; void *
0x140031505  mov     r8d, edi; Size
0x140031508  xor     edx, edx; Val
0x14003150a  call    memset_0
0x14003150f  mov     ebx, 208h
0x140031514  lea     rcx, [rbp+3C0h+var_428]; void *
0x140031518  mov     r8d, ebx; Size
0x14003151b  xor     edx, edx; Val
0x14003151d  call    memset_0
0x140031522  mov     r8d, ebx; Size
0x140031525  lea     rcx, [rbp+3C0h+FileName]; void *
0x14003152c  xor     edx, edx; Val
0x14003152e  call    memset_0
0x140031533  movups  xmm0, cs:xmmword_14006A7A8
0x14003153a  lea     r8, [rsp+4C0h+Properties]; Properties
0x14003153f  mov     [rsp+4C0h+Properties.Wnode.BufferSize], 488h
0x140031547  lea     rdx, InstanceName; "WER Tracing Session"
0x14003154e  mov     [rsp+4C0h+Properties.Wnode.ClientContext], 1
0x140031556  xor     ecx, ecx; TraceHandle
0x140031558  mov     [rsp+4C0h+Properties.Wnode.Flags], 20000h
0x140031560  movdqu  xmmword ptr [rsp+4C0h+Properties.Wnode.Guid.Data1], xmm0
0x140031566  mov     [rsp+4C0h+Properties.MaximumFileSize], 2
0x14003156e  mov     [rsp+4C0h+Properties.LogFileMode], 1020802h
0x140031576  mov     [rbp+3C0h+Properties.LoggerNameOffset], edi
0x140031579  mov     [rbp+3C0h+Properties.LogFileNameOffset], 280h
0x140031580  call    cs:__imp_QueryTraceW
0x140031587  nop     dword ptr [rax+rax+00h]
0x14003158c  xor     ebx, ebx
0x14003158e  test    eax, eax
0x140031590  jnz     loc_140031666
0x140031596  lea     r8, [rsp+4C0h+Properties]; Properties
0x14003159b  xor     ecx, ecx; TraceHandle
0x14003159d  lea     rdx, InstanceName; "WER Tracing Session"
0x1400315a4  call    cs:__imp_StopTraceW
0x1400315ab  nop     dword ptr [rax+rax+00h]
0x1400315b0  lea     rdi, WPP_GLOBAL_Control
0x1400315b7  test    eax, eax
0x1400315b9  jz      short loc_1400315FD
0x1400315bb  call    cs:__imp_GetLastError
0x1400315c2  nop     dword ptr [rax+rax+00h]
0x1400315c7  test    eax, eax
0x1400315c9  jle     short loc_1400315D3
0x1400315cb  movzx   eax, ax
0x1400315ce  or      eax, 80070000h
0x1400315d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400315da  cmp     rcx, rdi
0x1400315dd  jz      short loc_1400315FD
0x1400315df  test    byte ptr [rcx+1Ch], 1
0x1400315e3  jz      short loc_1400315FD
0x1400315e5  mov     rcx, [rcx+10h]
0x1400315e9  lea     r8, WPP_495391dabb8f3fb26262efb7112a6047_Traceguids
0x1400315f0  mov     edx, 0Fh
0x1400315f5  mov     r9d, eax
0x1400315f8  call    WPP_SF_d
0x1400315fd  cmp     [rbp+3C0h+FileName], bx
0x140031604  jz      short loc_140031666
0x140031606  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x14003160d  call    cs:__imp_DeleteFileW
0x140031614  nop     dword ptr [rax+rax+00h]
0x140031619  test    eax, eax
0x14003161b  jnz     short loc_140031666
0x14003161d  mov     rax, cs:WPP_GLOBAL_Control
0x140031624  cmp     rax, rdi
0x140031627  jz      short loc_140031666
0x140031629  test    byte ptr [rax+1Ch], 1
0x14003162d  jz      short loc_140031666
0x14003162f  call    cs:__imp_GetLastError
0x140031636  nop     dword ptr [rax+rax+00h]
0x14003163b  test    eax, eax
0x14003163d  jle     short loc_140031647
0x14003163f  movzx   eax, ax
0x140031642  or      eax, 80070000h
0x140031647  mov     rcx, cs:WPP_GLOBAL_Control
0x14003164e  lea     r8, WPP_495391dabb8f3fb26262efb7112a6047_Traceguids
0x140031655  mov     edx, 10h
0x14003165a  mov     r9d, eax
0x14003165d  mov     rcx, [rcx+10h]
0x140031661  call    WPP_SF_d
0x140031666  xor     eax, eax
0x140031668  mov     rcx, [rbp+3C0h+var_10]
0x14003166f  xor     rcx, rsp; StackCookie
0x140031672  call    __security_check_cookie
0x140031677  lea     r11, [rsp+4C0h+var_s0]
0x14003167f  mov     rbx, [r11+10h]
0x140031683  mov     rdi, [r11+18h]
0x140031687  mov     rsp, r11
0x14003168a  pop     rbp
0x14003168b  retn
```
