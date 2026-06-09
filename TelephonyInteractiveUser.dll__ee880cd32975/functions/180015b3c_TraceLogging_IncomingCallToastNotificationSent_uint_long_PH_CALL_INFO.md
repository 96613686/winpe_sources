# TraceLogging::IncomingCallToastNotificationSent(uint,long,PH_CALL_INFO *)

- ea: `0x180015b3c`
- end: `0x180015cec`
- name: `?IncomingCallToastNotificationSent@TraceLogging@@SAXIJPEAUPH_CALL_INFO@@@Z`
- size: `432`
- prototype: `void __fastcall(unsigned int, int, struct PH_CALL_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800152a0`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x180015b3c`

## string_xrefs

- `0x180015c74`: `IncomingCallToastStatics: Show, callId`

## pseudocode

```c
void __fastcall TraceLogging::IncomingCallToastNotificationSent(int a1, int a2, struct PH_CALL_INFO *a3)
{
  const unsigned __int16 *v4; // rcx
  __int64 v5; // rax
  const unsigned __int16 *v6; // rdx
  int v7; // r10d
  __int64 v8; // r9
  int v9; // r9d
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // [rsp+30h] [rbp-79h] BYREF
  int v13; // [rsp+34h] [rbp-75h] BYREF
  int v14; // [rsp+38h] [rbp-71h] BYREF
  __int64 v15; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+50h] [rbp-59h] BYREF
  int *v17; // [rsp+70h] [rbp-39h]
  __int64 v18; // [rsp+78h] [rbp-31h]
  __int64 *v19; // [rsp+80h] [rbp-29h]
  __int64 v20; // [rsp+88h] [rbp-21h]
  const char *v21; // [rsp+90h] [rbp-19h]
  __int64 v22; // [rsp+98h] [rbp-11h]
  int *v23; // [rsp+A0h] [rbp-9h]
  __int64 v24; // [rsp+A8h] [rbp-1h]
  int *v25; // [rsp+B0h] [rbp+7h]
  __int64 v26; // [rsp+B8h] [rbp+Fh]
  struct PH_CALL_INFO *v27; // [rsp+C0h] [rbp+17h]
  int v28; // [rsp+C8h] [rbp+1Fh]
  int v29; // [rsp+CCh] [rbp+23h]
  const unsigned __int16 *v30; // [rsp+D0h] [rbp+27h]
  int v31; // [rsp+D8h] [rbp+2Fh]
  int v32; // [rsp+DCh] [rbp+33h]
  const unsigned __int16 *v33; // [rsp+E0h] [rbp+37h]
  int v34; // [rsp+E8h] [rbp+3Fh]
  int v35; // [rsp+ECh] [rbp+43h]

  if ( (unsigned int)dword_180025000 > 5
    && (qword_180025010 & 0x400000000000LL) != 0
    && (qword_180025018 & 0x400000000000LL) == qword_180025018 )
  {
    v12 = a2;
    v4 = (const unsigned __int16 *)((char *)a3 + 1392);
    v13 = a1;
    v5 = -1;
    v14 = a1;
    v15 = 0x1000000;
    v6 = (const unsigned __int16 *)((char *)a3 + 416);
    v7 = 2;
    if ( a3 == (struct PH_CALL_INFO *)-1392LL )
    {
      v4 = &dword_18001D6C4;
      v9 = 2;
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( v4[v8] );
      v9 = 2 * v8 + 2;
    }
    v33 = v4;
    v34 = v9;
    v35 = 0;
    if ( a3 == (struct PH_CALL_INFO *)-416LL )
    {
      v6 = &dword_18001D6C4;
      v11 = 2;
    }
    else
    {
      v10 = -1;
      do
        ++v10;
      while ( v6[v10] );
      v11 = 2 * v10 + 2;
    }
    v30 = v6;
    v31 = v11;
    v32 = 0;
    if ( a3 )
    {
      do
        ++v5;
      while ( *((_WORD *)a3 + v5) );
      v7 = 2 * v5 + 2;
    }
    else
    {
      a3 = (struct PH_CALL_INFO *)&dword_18001D6C4;
    }
    v27 = a3;
    v25 = &v12;
    v28 = v7;
    v23 = &v13;
    v29 = 0;
    v21 = "IncomingCallToastStatics: Show, callId";
    v26 = 4;
    v19 = &v15;
    v24 = 4;
    v17 = &v14;
    v22 = 39;
    v20 = 8;
    v18 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025000, (unsigned __int8 *)&word_18002106A, 0, 0, 0xAu, &v16);
  }
}

```

## disassembly

```asm
0x180015b3c  push    rbp
0x180015b3e  lea     rbp, [rsp-57h]
0x180015b43  sub     rsp, 100h
0x180015b4a  mov     rax, cs:__security_cookie
0x180015b51  xor     rax, rsp
0x180015b54  mov     [rbp+57h+var_10], rax
0x180015b58  mov     eax, cs:dword_180025000
0x180015b5e  mov     r11d, edx
0x180015b61  mov     r10d, ecx
0x180015b64  cmp     eax, 5
0x180015b67  jbe     loc_180015CD7
0x180015b6d  mov     r9, cs:qword_180025018
0x180015b74  mov     rcx, 400000000000h
0x180015b7e  mov     rax, cs:qword_180025010
0x180015b85  test    rcx, rax
0x180015b88  jz      loc_180015CD7
0x180015b8e  mov     rax, r9
0x180015b91  and     rax, rcx
0x180015b94  cmp     rax, r9
0x180015b97  jnz     loc_180015CD7
0x180015b9d  mov     [rbp+57h+var_D0], r11d
0x180015ba1  lea     rcx, [r8+570h]
0x180015ba8  xor     r11d, r11d
0x180015bab  mov     [rbp+57h+var_CC], r10d
0x180015baf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015bb3  mov     [rbp+57h+var_C8], r10d
0x180015bb7  mov     [rbp+57h+var_C0], 1000000h
0x180015bbf  lea     rdx, [r8+1A0h]
0x180015bc6  mov     r10d, 2
0x180015bcc  test    rcx, rcx
0x180015bcf  jz      short loc_180015BE8
0x180015bd1  mov     r9, rax
0x180015bd4  inc     r9
0x180015bd7  cmp     [rcx+r9*2], r11w
0x180015bdc  jnz     short loc_180015BD4
0x180015bde  lea     r9d, ds:2[r9*2]
0x180015be6  jmp     short loc_180015BF2
0x180015be8  lea     rcx, dword_18001D6C4
0x180015bef  mov     r9d, r10d
0x180015bf2  mov     [rbp+57h+var_20], rcx
0x180015bf6  mov     [rbp+57h+var_18], r9d
0x180015bfa  mov     [rbp+57h+var_14], r11d
0x180015bfe  test    rdx, rdx
0x180015c01  jz      short loc_180015C19
0x180015c03  mov     rcx, rax
0x180015c06  inc     rcx
0x180015c09  cmp     [rdx+rcx*2], r11w
0x180015c0e  jnz     short loc_180015C06
0x180015c10  lea     ecx, ds:2[rcx*2]
0x180015c17  jmp     short loc_180015C23
0x180015c19  lea     rdx, dword_18001D6C4
0x180015c20  mov     ecx, r10d
0x180015c23  mov     [rbp+57h+var_30], rdx
0x180015c27  mov     [rbp+57h+var_28], ecx
0x180015c2a  mov     [rbp+57h+var_24], r11d
0x180015c2e  test    r8, r8
0x180015c31  jz      short loc_180015C47
0x180015c33  inc     rax
0x180015c36  cmp     [r8+rax*2], r11w
0x180015c3b  jnz     short loc_180015C33
0x180015c3d  lea     r10d, ds:2[rax*2]
0x180015c45  jmp     short loc_180015C4E
0x180015c47  lea     r8, dword_18001D6C4
0x180015c4e  lea     rax, [rbp+57h+var_D0]
0x180015c52  mov     [rbp+57h+var_40], r8
0x180015c56  mov     [rbp+57h+var_50], rax
0x180015c5a  lea     rdx, word_18002106A; int
0x180015c61  lea     rax, [rbp+57h+var_CC]
0x180015c65  mov     [rbp+57h+var_38], r10d
0x180015c69  mov     [rbp+57h+var_60], rax
0x180015c6d  lea     rcx, dword_180025000; int
0x180015c74  lea     rax, aIncomingcallto_5; "IncomingCallToastStatics: Show, callId"
0x180015c7b  mov     [rbp+57h+var_34], r11d
0x180015c7f  mov     [rbp+57h+var_70], rax
0x180015c83  xor     r9d, r9d; int
0x180015c86  lea     rax, [rbp+57h+var_C0]
0x180015c8a  mov     [rbp+57h+var_48], 4
0x180015c92  mov     [rbp+57h+var_80], rax
0x180015c96  xor     r8d, r8d; int
0x180015c99  lea     rax, [rbp+57h+var_C8]
0x180015c9d  mov     [rbp+57h+var_58], 4
0x180015ca5  mov     [rbp+57h+var_90], rax
0x180015ca9  lea     rax, [rbp+57h+var_B0]
0x180015cad  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x180015cb2  mov     [rsp+100h+var_E0], 0Ah; ULONG
0x180015cba  mov     [rbp+57h+var_68], 27h ; '''
0x180015cc2  mov     [rbp+57h+var_78], 8
0x180015cca  mov     [rbp+57h+var_88], 4
0x180015cd2  call    _tlgWriteTransfer_EventWriteTransfer
0x180015cd7  mov     rcx, [rbp+57h+var_10]
0x180015cdb  xor     rcx, rsp; StackCookie
0x180015cde  call    __security_check_cookie
0x180015ce3  add     rsp, 100h
0x180015cea  pop     rbp
0x180015ceb  retn
```
