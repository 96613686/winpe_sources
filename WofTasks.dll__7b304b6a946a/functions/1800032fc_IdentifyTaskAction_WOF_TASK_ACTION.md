# IdentifyTaskAction(_WOF_TASK_ACTION *)

- ea: `0x1800032fc`
- end: `0x1800034fd`
- name: `?IdentifyTaskAction@@YAJPEAW4_WOF_TASK_ACTION@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(enum _WOF_TASK_ACTION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003ac0`

## callees

- `0x1800032fc`
- `0x1800043d8`
- `0x18000518e`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000343b`
- `KERNEL32!GetLastError` at `0x18000343b`
- `FVEAPI!FveGetStatusW` at `0x180003478`
- `FVEAPI!FveGetStatusW` at `0x180003478`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003381`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003381`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800034a7`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800034a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180003431`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180003431`

## string_xrefs

- `0x180003359`: `WofTaskAction`

## pseudocode

```c
__int64 __fastcall IdentifyTaskAction(enum _WOF_TASK_ACTION *a1)
{
  unsigned int v2; // eax
  unsigned int StatusW; // ebx
  const wchar_t *v4; // rcx
  __int64 v5; // rdx
  _WORD *v6; // r8
  __int64 v7; // rax
  __int64 v8; // r10
  __int64 v9; // r9
  _WORD *v10; // rcx
  UINT v11; // edi
  WCHAR *v12; // rbx
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // eax
  const EVENT_DESCRIPTOR *v15; // rdx
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v19[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+5Ch] [rbp-A4h]
  _WORD v21[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v19, 0, 0x90u);
  pcbData[0] = 4;
  pvData = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\Overrides",
         L"WofTaskAction",
         0x10u,
         0,
         &pvData,
         pcbData) )
  {
    v4 = L"\\\\.\\";
    v5 = 260;
    v6 = v21;
    v7 = 2147483646;
    v8 = 0;
    do
    {
      if ( !v7 )
        break;
      if ( !*v4 )
        break;
      *v6++ = *v4++;
      --v7;
      ++v8;
      --v5;
    }
    while ( v5 );
    v9 = v8 - 1;
    v10 = v6 - 1;
    if ( v5 )
      v9 = v8;
    StatusW = v5 == 0 ? 0x8007007A : 0;
    if ( v5 )
      v10 = v6;
    *v10 = 0;
    if ( !v5 )
      goto LABEL_30;
    v11 = 260 - v9;
    if ( (unsigned __int64)(260 - v9) > 0xFFFFFFFF )
    {
      StatusW = -2147024362;
    }
    else
    {
      v12 = &v21[v9];
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v12, v11);
      if ( SystemWindowsDirectoryW )
      {
        if ( SystemWindowsDirectoryW <= v11 )
          v12[2] = 0;
      }
      else
      {
        LastError = GetLastError();
        StatusW = LastError;
        if ( LastError > 0 )
          StatusW = (unsigned __int16)LastError | 0x80070000;
        if ( StatusW )
          goto LABEL_30;
      }
      v19[0] = 144;
      v19[1] = 10;
      StatusW = FveGetStatusW(v21, v19);
      if ( !StatusW )
      {
        v2 = (v20 & 1) == 0;
        goto LABEL_23;
      }
    }
LABEL_30:
    if ( (StatusW & 0x80000000) != 0 )
      LogError(&WofTaskActionErrorEventId, StatusW);
    return StatusW;
  }
  v2 = pvData;
  StatusW = 0;
  if ( pvData <= 2 )
  {
LABEL_23:
    *(_DWORD *)a1 = v2;
    goto LABEL_24;
  }
  v2 = *(_DWORD *)a1;
LABEL_24:
  if ( v2 )
  {
    if ( v2 != 1 )
      return StatusW;
    v15 = (const EVENT_DESCRIPTOR *)WofTaskActionDeleteHashesEventId;
  }
  else
  {
    v15 = &WofTaskActionGenerateHashesEventId;
  }
  EventWrite(RegHandle, v15, 0, 0);
  return StatusW;
}

```

## disassembly

```asm
0x1800032fc  mov     [rsp-8+arg_8], rbx
0x180003301  mov     [rsp-8+arg_10], rsi
0x180003306  push    rbp
0x180003307  push    rdi
0x180003308  push    r14
0x18000330a  lea     rbp, [rsp-200h]
0x180003312  sub     rsp, 300h
0x180003319  mov     rax, cs:__security_cookie
0x180003320  xor     rax, rsp
0x180003323  mov     [rbp+210h+var_20], rax
0x18000332a  mov     rsi, rcx
0x18000332d  xor     edx, edx; Val
0x18000332f  lea     rcx, [rsp+310h+var_2C0]; void *
0x180003334  mov     r8d, 90h; Size
0x18000333a  call    memset_0
0x18000333f  xor     r14d, r14d
0x180003342  mov     [rsp+310h+var_2CC], 4
0x18000334a  lea     rax, [rsp+310h+var_2CC]
0x18000334f  mov     [rsp+310h+var_2D0], r14d
0x180003354  mov     [rsp+310h+pcbData], rax; pcbData
0x180003359  lea     r8, Value; "WofTaskAction"
0x180003360  lea     rax, [rsp+310h+var_2D0]
0x180003365  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000336c  mov     [rsp+310h+pvData], rax; pvData
0x180003371  lea     r9d, [r14+10h]; dwFlags
0x180003375  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000337c  mov     [rsp+310h+pdwType], r14; pdwType
0x180003381  call    cs:__imp_RegGetValueW
0x180003387  test    eax, eax
0x180003389  jnz     short loc_1800033A2
0x18000338b  mov     eax, [rsp+310h+var_2D0]
0x18000338f  mov     ebx, r14d
0x180003392  cmp     eax, 2
0x180003395  jbe     loc_18000348D
0x18000339b  mov     eax, [rsi]
0x18000339d  jmp     loc_18000348F
0x1800033a2  mov     edi, 104h
0x1800033a7  lea     rcx, asc_180007B40; "\\\\.\\"
0x1800033ae  mov     edx, edi
0x1800033b0  lea     r8, [rbp+210h+var_230]
0x1800033b4  mov     eax, 7FFFFFFEh
0x1800033b9  mov     r10, r14
0x1800033bc  test    rax, rax
0x1800033bf  jz      short loc_1800033E3
0x1800033c1  movzx   r9d, word ptr [rcx]
0x1800033c5  test    r9w, r9w
0x1800033c9  jz      short loc_1800033E3
0x1800033cb  mov     [r8], r9w
0x1800033cf  add     rcx, 2
0x1800033d3  add     r8, 2
0x1800033d7  dec     rax
0x1800033da  inc     r10
0x1800033dd  sub     rdx, 1
0x1800033e1  jnz     short loc_1800033BC
0x1800033e3  test    rdx, rdx
0x1800033e6  lea     r9, [r10-1]
0x1800033ea  mov     rax, rdx
0x1800033ed  lea     rcx, [r8-2]
0x1800033f1  cmovnz  r9, r10
0x1800033f5  neg     rax
0x1800033f8  sbb     ebx, ebx
0x1800033fa  not     ebx
0x1800033fc  and     ebx, 8007007Ah
0x180003402  test    rdx, rdx
0x180003405  cmovnz  rcx, r8
0x180003409  mov     [rcx], r14w
0x18000340d  jz      loc_1800034C2
0x180003413  sub     rdi, r9
0x180003416  mov     eax, 0FFFFFFFFh
0x18000341b  cmp     rdi, rax
0x18000341e  ja      loc_1800034BD
0x180003424  lea     rbx, [rbp+210h+var_230]
0x180003428  mov     edx, edi; uSize
0x18000342a  lea     rbx, [rbx+r9*2]
0x18000342e  mov     rcx, rbx; lpBuffer
0x180003431  call    cs:__imp_GetSystemWindowsDirectoryW
0x180003437  test    eax, eax
0x180003439  jnz     short loc_180003456
0x18000343b  call    cs:__imp_GetLastError
0x180003441  mov     ebx, eax
0x180003443  test    eax, eax
0x180003445  jle     short loc_180003450
0x180003447  movzx   ebx, ax
0x18000344a  or      ebx, 80070000h
0x180003450  test    ebx, ebx
0x180003452  jz      short loc_18000345F
0x180003454  jmp     short loc_1800034C2
0x180003456  cmp     eax, edi
0x180003458  ja      short loc_18000345F
0x18000345a  mov     [rbx+4], r14w
0x18000345f  lea     rdx, [rsp+310h+var_2C0]
0x180003464  mov     [rsp+310h+var_2C0], 90h
0x18000346c  lea     rcx, [rbp+210h+var_230]
0x180003470  mov     [rsp+310h+var_2BC], 0Ah
0x180003478  call    cs:__imp_FveGetStatusW
0x18000347e  mov     ebx, eax
0x180003480  test    eax, eax
0x180003482  jnz     short loc_1800034C2
0x180003484  mov     eax, [rsp+310h+var_2B4]
0x180003488  not     eax
0x18000348a  and     eax, 1
0x18000348d  mov     [rsi], eax
0x18000348f  test    eax, eax
0x180003491  jnz     short loc_1800034AF
0x180003493  lea     rdx, WofTaskActionGenerateHashesEventId; EventDescriptor
0x18000349a  mov     rcx, cs:RegHandle; RegHandle
0x1800034a1  xor     r9d, r9d; UserData
0x1800034a4  xor     r8d, r8d; UserDataCount
0x1800034a7  call    cs:__imp_EventWrite
0x1800034ad  jmp     short loc_1800034D4
0x1800034af  cmp     eax, 1
0x1800034b2  jnz     short loc_1800034D4
0x1800034b4  lea     rdx, WofTaskActionDeleteHashesEventId
0x1800034bb  jmp     short loc_18000349A
0x1800034bd  mov     ebx, 80070216h
0x1800034c2  test    ebx, ebx
0x1800034c4  jns     short loc_1800034D4
0x1800034c6  mov     edx, ebx; int
0x1800034c8  lea     rcx, WofTaskActionErrorEventId; EventDescriptor
0x1800034cf  call    ?LogError@@YAXPEBU_EVENT_DESCRIPTOR@@H@Z; LogError(_EVENT_DESCRIPTOR const *,int)
0x1800034d4  mov     eax, ebx
0x1800034d6  mov     rcx, [rbp+210h+var_20]
0x1800034dd  xor     rcx, rsp; StackCookie
0x1800034e0  call    __security_check_cookie
0x1800034e5  lea     r11, [rsp+310h+var_10]
0x1800034ed  mov     rbx, [r11+28h]
0x1800034f1  mov     rsi, [r11+30h]
0x1800034f5  mov     rsp, r11
0x1800034f8  pop     r14
0x1800034fa  pop     rdi
0x1800034fb  pop     rbp
0x1800034fc  retn
```
