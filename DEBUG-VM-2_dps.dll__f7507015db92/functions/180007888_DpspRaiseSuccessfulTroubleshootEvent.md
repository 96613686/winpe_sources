# DpspRaiseSuccessfulTroubleshootEvent

- ea: `0x180007888`
- end: `0x180007a5d`
- name: `DpspRaiseSuccessfulTroubleshootEvent`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007a64`

## callees

- `0x180007888`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800079b1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800079c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800079b1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800079c7`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180007920`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180007920`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180007a1e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180007a1e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007948`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007a2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007948`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007a2d`

## pseudocode

```c
__int64 __fastcall DpspRaiseSuccessfulTroubleshootEvent(__int64 a1, __int64 a2, const EVENT_DESCRIPTOR *a3)
{
  unsigned int v6; // esi
  void *v7; // rcx
  DWORD LengthSid; // eax
  PSID v9; // rcx
  GUID ActivityId; // [rsp+30h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-69h] BYREF
  __int64 v13; // [rsp+50h] [rbp-59h]
  __int64 v14; // [rsp+58h] [rbp-51h]
  __int64 v15; // [rsp+60h] [rbp-49h]
  __int64 v16; // [rsp+68h] [rbp-41h]
  __int64 v17; // [rsp+70h] [rbp-39h]
  int v18; // [rsp+78h] [rbp-31h]
  int v19; // [rsp+7Ch] [rbp-2Dh]
  __int64 v20; // [rsp+80h] [rbp-29h]
  __int64 v21; // [rsp+88h] [rbp-21h]
  PSID v22; // [rsp+90h] [rbp-19h]
  DWORD v23; // [rsp+98h] [rbp-11h]
  int v24; // [rsp+9Ch] [rbp-Dh]
  __int64 v25; // [rsp+A0h] [rbp-9h]
  __int64 v26; // [rsp+A8h] [rbp-1h]
  __int64 v27; // [rsp+B0h] [rbp+7h]
  __int64 v28; // [rsp+B8h] [rbp+Fh]
  __int64 v29; // [rsp+C0h] [rbp+17h]
  __int64 v30; // [rsp+C8h] [rbp+1Fh]

  UserData.Ptr = 0;
  ActivityId = 0;
  memset_0(&UserData.Size, 0, 0x88u);
  if ( a1 )
  {
    v6 = 0;
    if ( EventEnabled(g_hETW, a3) )
    {
      if ( a1 != -24 )
        ActivityId = *(GUID *)(a1 + 24);
      EventActivityIdControl(4u, &ActivityId);
      v7 = *(void **)(a1 + 768);
      UserData.Ptr = *(_QWORD *)(a1 + 1216);
      v15 = a1 + 56;
      v17 = *(_QWORD *)(a2 + 128);
      v18 = *(_DWORD *)(a2 + 148);
      v20 = a1 + 40;
      *(_QWORD *)&UserData.Size = 16;
      v13 = a1 + 24;
      v14 = 16;
      v16 = 16;
      v19 = 0;
      v21 = 16;
      if ( v7 )
      {
        LengthSid = GetLengthSid(v7);
        v9 = *(PSID *)(a1 + 768);
      }
      else
      {
        LengthSid = GetLengthSid(g_pNullSid);
        v9 = g_pNullSid;
      }
      v23 = LengthSid;
      v22 = v9;
      v25 = a1 + 108;
      v24 = 0;
      v27 = a1 + 120;
      v26 = 4;
      v28 = 8;
      v29 = a2;
      v30 = 16;
      EventWrite(g_hETW, a3, 9u, &UserData);
      EventActivityIdControl(2u, &ActivityId);
    }
  }
  else
  {
    v6 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
      (int)L"DpspRaiseSuccessfulTroubleshootEvent",
      233,
      (int)L"Error = %d",
      87);
  }
  return v6;
}

```

## disassembly

```asm
0x180007888  mov     [rsp-8+arg_8], rbx
0x18000788d  mov     [rsp-8+arg_18], rsi
0x180007892  push    rbp
0x180007893  push    rdi
0x180007894  push    r13
0x180007896  push    r14
0x180007898  push    r15
0x18000789a  lea     rbp, [rsp-37h]
0x18000789f  sub     rsp, 0E0h
0x1800078a6  mov     rax, cs:__security_cookie
0x1800078ad  xor     rax, rsp
0x1800078b0  mov     [rbp+57h+var_30], rax
0x1800078b4  mov     r14, r8
0x1800078b7  mov     [rbp+57h+UserData.Ptr], 0
0x1800078bf  mov     r15, rdx
0x1800078c2  mov     rbx, rcx
0x1800078c5  xorps   xmm0, xmm0
0x1800078c8  lea     rcx, [rbp+57h+UserData.Size]; void *
0x1800078cc  xor     edx, edx; Val
0x1800078ce  mov     r8d, 88h; Size
0x1800078d4  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800078d8  call    memset_0
0x1800078dd  test    rbx, rbx
0x1800078e0  jnz     short loc_180007914
0x1800078e2  lea     r9, aErrorD; "Error = %d"
0x1800078e9  mov     dword ptr [rsp+100h+Args], 57h ; 'W'; Args
0x1800078f1  mov     r8d, 0E9h; int
0x1800078f7  lea     rdx, aDpspraisesucce; "DpspRaiseSuccessfulTroubleshootEvent"
0x1800078fe  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007905  mov     esi, 80070057h
0x18000790a  call    WdipTraceError
0x18000790f  jmp     loc_180007A33
0x180007914  mov     rcx, cs:g_hETW; RegHandle
0x18000791b  mov     rdx, r14; EventDescriptor
0x18000791e  xor     esi, esi
0x180007920  call    cs:__imp_EventEnabled
0x180007926  test    al, al
0x180007928  jz      loc_180007A33
0x18000792e  lea     rdi, [rbx+18h]
0x180007932  test    rdi, rdi
0x180007935  jz      short loc_18000793F
0x180007937  movups  xmm0, xmmword ptr [rdi]
0x18000793a  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18000793f  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180007943  mov     ecx, 4; ControlCode
0x180007948  call    cs:__imp_EventActivityIdControl
0x18000794e  mov     rax, [rbx+4C0h]
0x180007955  mov     rcx, [rbx+300h]; pSid
0x18000795c  mov     [rbp+57h+UserData.Ptr], rax
0x180007960  lea     rax, [rbx+38h]
0x180007964  mov     [rbp+57h+var_A0], rax
0x180007968  mov     rax, [r15+80h]
0x18000796f  mov     [rbp+57h+var_90], rax
0x180007973  mov     eax, [r15+94h]
0x18000797a  mov     [rbp+57h+var_88], eax
0x18000797d  lea     rax, [rbx+28h]
0x180007981  mov     [rbp+57h+var_80], rax
0x180007985  mov     qword ptr [rbp+57h+UserData.Size], 10h
0x18000798d  mov     [rbp+57h+var_B0], rdi
0x180007991  mov     [rbp+57h+var_A8], 10h
0x180007999  mov     [rbp+57h+var_98], 10h
0x1800079a1  mov     [rbp+57h+var_84], esi
0x1800079a4  mov     [rbp+57h+var_78], 10h
0x1800079ac  test    rcx, rcx
0x1800079af  jz      short loc_1800079C0
0x1800079b1  call    cs:__imp_GetLengthSid
0x1800079b7  mov     rcx, [rbx+300h]
0x1800079be  jmp     short loc_1800079D4
0x1800079c0  mov     rcx, cs:g_pNullSid; pSid
0x1800079c7  call    cs:__imp_GetLengthSid
0x1800079cd  mov     rcx, cs:g_pNullSid
0x1800079d4  mov     [rbp+57h+var_68], eax
0x1800079d7  lea     r9, [rbp+57h+UserData]; UserData
0x1800079db  lea     rax, [rbx+6Ch]
0x1800079df  mov     [rbp+57h+var_70], rcx
0x1800079e3  mov     rcx, cs:g_hETW; RegHandle
0x1800079ea  mov     r8d, 9; UserDataCount
0x1800079f0  mov     [rbp+57h+var_60], rax
0x1800079f4  mov     rdx, r14; EventDescriptor
0x1800079f7  lea     rax, [rbx+78h]
0x1800079fb  mov     [rbp+57h+var_64], esi
0x1800079fe  mov     [rbp+57h+var_50], rax
0x180007a02  mov     [rbp+57h+var_58], 4
0x180007a0a  mov     [rbp+57h+var_48], 8
0x180007a12  mov     [rbp+57h+var_40], r15
0x180007a16  mov     [rbp+57h+var_38], 10h
0x180007a1e  call    cs:__imp_EventWrite
0x180007a24  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180007a28  mov     ecx, 2; ControlCode
0x180007a2d  call    cs:__imp_EventActivityIdControl
0x180007a33  mov     eax, esi
0x180007a35  mov     rcx, [rbp+57h+var_30]
0x180007a39  xor     rcx, rsp; StackCookie
0x180007a3c  call    __security_check_cookie
0x180007a41  lea     r11, [rsp+100h+var_20]
0x180007a49  mov     rbx, [r11+38h]
0x180007a4d  mov     rsi, [r11+48h]
0x180007a51  mov     rsp, r11
0x180007a54  pop     r15
0x180007a56  pop     r14
0x180007a58  pop     r13
0x180007a5a  pop     rdi
0x180007a5b  pop     rbp
0x180007a5c  retn
```
