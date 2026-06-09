# EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)

- ea: `0x1800067c0`
- end: `0x18000697a`
- name: `?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ`
- size: `442`
- prototype: `void(PCEVENT_DESCRIPTOR EventDescriptor, void *, ...)`
- caller_count: `17`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000523c`
- `0x180006070`
- `0x180006c5c`
- `0x180008720`
- `0x180008ab0`
- `0x18000936c`
- `0x180009b40`
- `0x18000a15c`
- `0x18000a6c0`
- `0x18000a780`
- `0x180011930`
- `0x180015990`
- `0x18001ad50`
- `0x18001b450`
- `0x18001b4f0`
- `0x18001b8e0`
- `0x18001d1f0`

## callees

- `0x1800066ac`
- `0x1800067c0`
- `0x18002120a`
- `0x180021240`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180006959`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180006959`

## pseudocode

```c
void EtwTraceMessage(PCEVENT_DESCRIPTOR EventDescriptor, void *a2, ...)
{
  va_list v3; // r9
  ULONG v4; // r8d
  va_list v5; // rdx
  __int64 v6; // rcx
  ULONGLONG v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // [rsp+28h] [rbp-E0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-D0h] BYREF
  int *v13; // [rsp+48h] [rbp-C0h]
  __int64 v14; // [rsp+50h] [rbp-B8h]
  void *v15; // [rsp+58h] [rbp-B0h]
  __int64 v16; // [rsp+60h] [rbp-A8h]
  char *v17; // [rsp+68h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-98h]
  __int64 *v19; // [rsp+78h] [rbp-90h]
  __int64 v20; // [rsp+80h] [rbp-88h]
  int *v21; // [rsp+88h] [rbp-80h]
  __int64 v22; // [rsp+90h] [rbp-78h]
  int *v23; // [rsp+98h] [rbp-70h]
  int v24; // [rsp+A0h] [rbp-68h]
  int v25; // [rsp+A4h] [rbp-64h]
  void *v26; // [rsp+880h] [rbp+778h] BYREF
  va_list va; // [rsp+888h] [rbp+780h] BYREF

  va_start(va, a2);
  v26 = a2;
  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0x7F8u);
  v11 = -557842430;
  if ( `EtwTraceMessage'::`2'::Module != -1 )
  {
    if ( !`EtwTraceMessage'::`2'::Module )
      EtwInitializeTraceMessaging((struct _TRACE_MESSAGE_MODULE *)&`EtwTraceMessage'::`2'::Module);
    *(_QWORD *)&UserData.Size = 8;
    UserData.Ptr = (ULONGLONG)&v26;
    va_copy(v3, va);
    v14 = 4;
    v13 = &v11;
    v4 = 7;
    v15 = &`EtwTraceMessage'::`2'::Module;
    v17 = byte_18002D978;
    v19 = qword_18002D968;
    v21 = &dword_18002D97C;
    v23 = &dword_18002D984;
    v24 = dword_18002D980;
    v16 = 8;
    v18 = 4;
    v20 = 16;
    v22 = 4;
    v25 = 0;
    while ( 1 )
    {
      v5 = v3 + 8;
      v3 += 16;
      v6 = *((_QWORD *)v3 - 1);
      if ( v6 == -1 )
      {
LABEL_18:
        EventWrite(MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context, EventDescriptor, v4, &UserData);
        return;
      }
      v7 = *((_QWORD *)v5 - 1);
      if ( v6 == -3 )
        break;
      if ( v6 == -2 )
      {
        if ( v7 )
        {
          v8 = -1;
          do
            ++v8;
          while ( *(_WORD *)(v7 + 2 * v8) );
          LODWORD(v6) = 2 * v8 + 2;
          goto LABEL_17;
        }
        goto LABEL_16;
      }
LABEL_17:
      v10 = v4++;
      v10 *= 2;
      *(&UserData.Ptr + v10) = v7;
      *(&UserData.Size + 2 * v10) = v6;
      *(&UserData.Reserved + 2 * v10) = 0;
      if ( v4 >= 0x80 )
        goto LABEL_18;
    }
    if ( v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_BYTE *)(v7 + v9) );
      LODWORD(v6) = v9 + 1;
      goto LABEL_17;
    }
LABEL_16:
    LODWORD(v6) = 0;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800067c0  mov     rax, rsp
0x1800067c3  mov     [rax+10h], rdx
0x1800067c7  mov     [rax+18h], r8
0x1800067cb  mov     [rax+20h], r9
0x1800067cf  push    rbp
0x1800067d0  push    rbx
0x1800067d1  push    rsi
0x1800067d2  push    rdi
0x1800067d3  lea     rbp, [rax-768h]
0x1800067da  sub     rsp, 848h
0x1800067e1  mov     rax, cs:__security_cookie
0x1800067e8  xor     rax, rsp
0x1800067eb  mov     [rbp+760h+var_30], rax
0x1800067f2  mov     rbx, rcx
0x1800067f5  xor     edi, edi
0x1800067f7  lea     rcx, [rsp+860h+UserData.Size]; void *
0x1800067fc  mov     [rsp+860h+UserData.Ptr], rdi
0x180006801  xor     edx, edx; Val
0x180006803  mov     r8d, 7F8h; Size
0x180006809  call    memset_0
0x18000680e  mov     rax, cs:?Module@?1??EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ@4U_TRACE_MESSAGE_MODULE@@A; _TRACE_MESSAGE_MODULE `EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)'::`2'::Module
0x180006815  mov     [rsp+860h+var_840], 0DEC00002h
0x18000681d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006821  jz      loc_18000695F
0x180006827  lea     rsi, ?Module@?1??EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ@4U_TRACE_MESSAGE_MODULE@@A; _TRACE_MESSAGE_MODULE `EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)'::`2'::Module
0x18000682e  test    rax, rax
0x180006831  jnz     short loc_18000683B
0x180006833  mov     rcx, rsi; struct _TRACE_MESSAGE_MODULE *
0x180006836  call    ?EtwInitializeTraceMessaging@@YAXPEAU_TRACE_MESSAGE_MODULE@@@Z; EtwInitializeTraceMessaging(_TRACE_MESSAGE_MODULE *)
0x18000683b  lea     rax, [rbp+760h+arg_8]
0x180006842  mov     qword ptr [rsp+860h+UserData.Size], 8
0x18000684b  mov     [rsp+860h+UserData.Ptr], rax
0x180006850  lea     r9, [rbp+760h+arg_10]
0x180006857  lea     rax, [rsp+860h+var_840]
0x18000685c  mov     [rsp+860h+var_818], 4
0x180006865  mov     [rsp+860h+var_820], rax
0x18000686a  mov     r8d, 7
0x180006870  lea     rax, byte_18002D978
0x180006877  mov     [rsp+860h+var_810], rsi
0x18000687c  mov     [rsp+860h+var_800], rax
0x180006881  lea     rax, qword_18002D968
0x180006888  mov     [rsp+860h+var_7F0], rax
0x18000688d  lea     rax, dword_18002D97C
0x180006894  mov     [rbp+760h+var_7E0], rax
0x180006898  lea     rax, dword_18002D984
0x18000689f  mov     [rbp+760h+var_7D0], rax
0x1800068a3  mov     eax, cs:dword_18002D980
0x1800068a9  mov     [rbp+760h+var_7C8], eax
0x1800068ac  mov     [rsp+860h+var_808], 8
0x1800068b5  mov     [rsp+860h+var_7F8], 4
0x1800068be  mov     [rsp+860h+var_7E8], 10h
0x1800068c7  mov     [rbp+760h+var_7D8], 4
0x1800068cf  mov     [rbp+760h+var_7C4], edi
0x1800068d2  lea     rdx, [r9+8]
0x1800068d6  lea     r9, [rdx+8]
0x1800068da  mov     rcx, [r9-8]
0x1800068de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800068e2  jz      short loc_18000694A
0x1800068e4  mov     rdx, [rdx-8]
0x1800068e8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800068ec  jz      short loc_18000690F
0x1800068ee  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x1800068f2  jnz     short loc_18000692B
0x1800068f4  test    rdx, rdx
0x1800068f7  jz      short loc_180006928
0x1800068f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800068fd  inc     rax
0x180006900  cmp     [rdx+rax*2], di
0x180006904  jnz     short loc_1800068FD
0x180006906  lea     ecx, [rax+rax]
0x180006909  add     rcx, 2
0x18000690d  jmp     short loc_18000692B
0x18000690f  test    rdx, rdx
0x180006912  jz      short loc_180006928
0x180006914  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006918  inc     rax
0x18000691b  cmp     [rdx+rax], dil
0x18000691f  jnz     short loc_180006918
0x180006921  mov     ecx, eax
0x180006923  inc     rcx
0x180006926  jmp     short loc_18000692B
0x180006928  mov     rcx, rdi
0x18000692b  mov     eax, r8d
0x18000692e  inc     r8d; UserDataCount
0x180006931  add     rax, rax
0x180006934  mov     [rsp+rax*8+860h+UserData.Ptr], rdx
0x180006939  mov     [rsp+rax*8+860h+UserData.Size], ecx
0x18000693d  mov     dword ptr [rsp+rax*8+860h+UserData.0Ch], edi
0x180006941  cmp     r8d, 80h
0x180006948  jb      short loc_1800068D2
0x18000694a  mov     rcx, cs:MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context; RegHandle
0x180006951  lea     r9, [rsp+860h+UserData]; UserData
0x180006956  mov     rdx, rbx; EventDescriptor
0x180006959  call    cs:__imp_EventWrite
0x18000695f  mov     rcx, [rbp+760h+var_30]
0x180006966  xor     rcx, rsp; StackCookie
0x180006969  call    __security_check_cookie
0x18000696e  add     rsp, 848h
0x180006975  pop     rdi
0x180006976  pop     rsi
0x180006977  pop     rbx
0x180006978  pop     rbp
0x180006979  retn
```
