# IkeDumpAcquire

- ea: `0x180038fc0`
- end: `0x180039402`
- name: `IkeDumpAcquire`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800bbdb0`

## callees

- `0x1800261c0`
- `0x180038fc0`
- `0x180050850`
- `0x18005bce4`
- `0x18006db48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039075`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800390ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003912b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039164`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800391df`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039218`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003928c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800392d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039075`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800390ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003912b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039164`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800391df`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039218`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003928c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800392d1`
- `ntdll!EtwEventWriteTransfer` at `0x1800393e5`
- `ntdll!EtwEventWriteTransfer` at `0x1800393e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180038ffb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180038ffb`

## pseudocode

```c
__int64 __fastcall IkeDumpAcquire(__int64 a1)
{
  _QWORD *v2; // rcx
  LPCRITICAL_SECTION v3; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v6; // r8
  __int64 v7; // rdi
  DWORD v8; // eax
  __int64 *v9; // rax
  __int64 v10; // r9
  LPCRITICAL_SECTION v11; // rdx
  DWORD v12; // eax
  LPVOID v13; // rax
  LPVOID v14; // r8
  __int64 v15; // rdi
  DWORD v16; // eax
  __int64 *v17; // rax
  __int64 v18; // r9
  LPCRITICAL_SECTION v19; // rdx
  DWORD v20; // eax
  LPVOID v21; // rax
  LPVOID v22; // r8
  __int64 v23; // rdi
  DWORD v24; // eax
  __int64 *v25; // rax
  __int64 v26; // r9
  __int64 result; // rax
  LPCRITICAL_SECTION v28; // rax
  DWORD v29; // ecx
  __int64 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // ecx
  char *v33; // rax
  const WCHAR *v34; // rdx
  __int64 v35; // rax
  int v37; // eax
  __int64 v38; // [rsp+28h] [rbp-71h]
  int v39; // [rsp+34h] [rbp-65h] BYREF
  int v40; // [rsp+38h] [rbp-61h] BYREF
  __int64 v41; // [rsp+40h] [rbp-59h] BYREF
  __int64 v42; // [rsp+48h] [rbp-51h] BYREF
  _DWORD v43[2]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v44; // [rsp+58h] [rbp-41h]
  char *v45; // [rsp+60h] [rbp-39h] BYREF
  int v46; // [rsp+68h] [rbp-31h]
  int v47; // [rsp+6Ch] [rbp-2Dh]
  char *v48; // [rsp+70h] [rbp-29h]
  int v49; // [rsp+78h] [rbp-21h]
  int v50; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v51; // [rsp+80h] [rbp-19h]
  __int64 v52; // [rsp+88h] [rbp-11h]
  const WCHAR *v53; // [rsp+90h] [rbp-9h]
  int v54; // [rsp+98h] [rbp-1h]
  int v55; // [rsp+9Ch] [rbp+3h]
  __int64 *v56; // [rsp+A0h] [rbp+7h]
  __int64 v57; // [rsp+A8h] [rbp+Fh]
  int *v58; // [rsp+B0h] [rbp+17h]
  __int64 v59; // [rsp+B8h] [rbp+1Fh]
  int *v60; // [rsp+C0h] [rbp+27h]
  __int64 v61; // [rsp+C8h] [rbp+2Fh]

  if ( !*(_DWORD *)(a1 + 184) || !*(_DWORD *)(a1 + 248) )
    DebugBreak();
  IkeAddrDump((__int16 *)"QM localAddr", (unsigned __int8 *)(a1 + 188));
  IkeAddrDump((__int16 *)"QM peerAddr", (unsigned __int8 *)(a1 + 252));
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v3 = gIkeExtGlobals;
      if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
      {
        v6 = 0;
      }
      else
      {
        Value = TlsGetValue(LockSemaphore);
        v2 = WPP_GLOBAL_Control;
        v6 = Value;
        v3 = gIkeExtGlobals;
      }
      v7 = (__int64)v6 + 8;
      if ( !v6 )
        v7 = 0;
      if ( v3
        && (v8 = (DWORD)v3[86].LockSemaphore, v8 != -1)
        && (v9 = (__int64 *)TlsGetValue(v8), v2 = WPP_GLOBAL_Control, v9) )
      {
        v10 = *v9;
      }
      else
      {
        LODWORD(v10) = 0;
      }
      WPP_SF_iSI(
        v2[2],
        25,
        (unsigned int)WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids,
        v10,
        v7,
        *(_QWORD *)(a1 + 320));
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)v2 + 25) >= 4u && (*((_BYTE *)v2 + 28) & 0x10) != 0 )
      {
        v11 = gIkeExtGlobals;
        if ( !gIkeExtGlobals || (v12 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v12 == -1) )
        {
          v14 = 0;
        }
        else
        {
          v13 = TlsGetValue(v12);
          v2 = WPP_GLOBAL_Control;
          v14 = v13;
          v11 = gIkeExtGlobals;
        }
        v15 = (__int64)v14 + 8;
        if ( !v14 )
          v15 = 0;
        if ( v11
          && (v16 = (DWORD)v11[86].LockSemaphore, v16 != -1)
          && (v17 = (__int64 *)TlsGetValue(v16), v2 = WPP_GLOBAL_Control, v17) )
        {
          v18 = *v17;
        }
        else
        {
          LODWORD(v18) = 0;
        }
        LODWORD(v38) = *(_DWORD *)(a1 + 328);
        WPP_SF_iSL(v2[2], 26, (unsigned int)WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids, v18, v15, v38);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_BYTE *)v2 + 28) & 0x10) != 0 )
      {
        v19 = gIkeExtGlobals;
        if ( !gIkeExtGlobals || (v20 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v20 == -1) )
        {
          v22 = 0;
        }
        else
        {
          v21 = TlsGetValue(v20);
          v2 = WPP_GLOBAL_Control;
          v22 = v21;
          v19 = gIkeExtGlobals;
        }
        v23 = (__int64)v22 + 8;
        if ( !v22 )
          v23 = 0;
        if ( v19
          && (v24 = (DWORD)v19[86].LockSemaphore, v24 != -1)
          && (v25 = (__int64 *)TlsGetValue(v24), v2 = WPP_GLOBAL_Control, v25) )
        {
          v26 = *v25;
        }
        else
        {
          LODWORD(v26) = 0;
        }
        LODWORD(v38) = *(_DWORD *)(a1 + 376);
        WPP_SF_iSL(v2[2], 27, (unsigned int)WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids, v26, v23, v38);
      }
    }
  }
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v29 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v29 != -1 )
      {
        v30 = (__int64 *)TlsGetValue(v29);
        if ( v30 )
        {
          v31 = *v30;
          v28 = gIkeExtGlobals;
LABEL_56:
          v41 = v31;
          v51 = &v41;
          v52 = 8;
          if ( !v28 )
            goto LABEL_64;
          v32 = (DWORD)v28[86].LockSemaphore;
          if ( v32 == -1 )
            goto LABEL_64;
          v33 = (char *)TlsGetValue(v32);
          v34 = (const WCHAR *)(v33 + 8);
          if ( !v33 )
            v34 = 0;
          if ( v34 )
          {
            v35 = -1;
            while ( v34[++v35] != 0 )
              ;
            v37 = 2 * v35 + 2;
          }
          else
          {
LABEL_64:
            v34 = &LocaleName;
            v37 = 2;
          }
          v54 = v37;
          v42 = *(_QWORD *)(a1 + 320);
          v53 = v34;
          v56 = &v42;
          v39 = *(_DWORD *)(a1 + 328);
          v58 = &v39;
          v40 = *(_DWORD *)(a1 + 376);
          v60 = &v40;
          v43[1] = 4;
          v45 = off_180173280;
          v55 = 0;
          v57 = 8;
          v59 = 4;
          v61 = 4;
          v43[0] = 184549376;
          v44 = 0;
          v46 = *(unsigned __int16 *)off_180173280;
          v48 = byte_18015ADFD;
          v47 = 2;
          v49 = 73;
          v50 = 1;
          return EtwEventWriteTransfer(qword_180173298, v43, 0, 0, 7, &v45);
        }
        v28 = gIkeExtGlobals;
      }
    }
    v31 = 0;
    goto LABEL_56;
  }
  return result;
}

```

## disassembly

```asm
0x180038fc0  push    rbp
0x180038fc2  push    rbx
0x180038fc3  push    rsi
0x180038fc4  lea     rbp, [rsp-47h]
0x180038fc9  sub     rsp, 0E0h
0x180038fd0  mov     rax, cs:__security_cookie
0x180038fd7  xor     rax, rsp
0x180038fda  mov     [rbp+57h+var_20], rax
0x180038fde  cmp     dword ptr [rcx+0B8h], 0
0x180038fe5  mov     rbx, rcx
0x180038fe8  mov     [rsp+0F0h+arg_10], r14
0x180038ff0  jz      short loc_180038FFB
0x180038ff2  cmp     dword ptr [rcx+0F8h], 0
0x180038ff9  jnz     short loc_180039001
0x180038ffb  call    cs:__imp_DebugBreak
0x180039001  lea     rdx, [rbx+0BCh]
0x180039008  lea     rcx, aQmLocaladdr; "QM localAddr"
0x18003900f  call    IkeAddrDump
0x180039014  lea     rdx, [rbx+0FCh]
0x18003901b  lea     rcx, aQmPeeraddr; "QM peerAddr"
0x180039022  call    IkeAddrDump
0x180039027  mov     rcx, cs:WPP_GLOBAL_Control
0x18003902e  lea     r14, WPP_GLOBAL_Control
0x180039035  xor     esi, esi
0x180039037  cmp     rcx, r14
0x18003903a  jz      loc_18003925E
0x180039040  cmp     byte ptr [rcx+19h], 4
0x180039044  mov     [rsp+0F0h+arg_8], rdi
0x18003904c  jb      loc_1800390F5
0x180039052  test    byte ptr [rcx+1Ch], 10h
0x180039056  jz      loc_1800390F5
0x18003905c  mov     rdx, cs:gIkeExtGlobals
0x180039063  test    rdx, rdx
0x180039066  jz      short loc_18003908E
0x180039068  mov     eax, [rdx+0D88h]
0x18003906e  cmp     eax, 0FFFFFFFFh
0x180039071  jz      short loc_18003908E
0x180039073  mov     ecx, eax; dwTlsIndex
0x180039075  call    cs:__imp_TlsGetValue
0x18003907b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039082  mov     r8, rax
0x180039085  mov     rdx, cs:gIkeExtGlobals
0x18003908c  jmp     short loc_180039091
0x18003908e  mov     r8, rsi
0x180039091  test    r8, r8
0x180039094  lea     rdi, [r8+8]
0x180039098  cmovz   rdi, rsi
0x18003909c  test    rdx, rdx
0x18003909f  jz      short loc_1800390C5
0x1800390a1  mov     eax, [rdx+0D88h]
0x1800390a7  cmp     eax, 0FFFFFFFFh
0x1800390aa  jz      short loc_1800390C5
0x1800390ac  mov     ecx, eax; dwTlsIndex
0x1800390ae  call    cs:__imp_TlsGetValue
0x1800390b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390bb  test    rax, rax
0x1800390be  jz      short loc_1800390C5
0x1800390c0  mov     r9, [rax]
0x1800390c3  jmp     short loc_1800390C8
0x1800390c5  mov     r9, rsi
0x1800390c8  mov     rax, [rbx+140h]
0x1800390cf  lea     r8, WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids
0x1800390d6  mov     rcx, [rcx+10h]
0x1800390da  mov     edx, 19h
0x1800390df  mov     [rsp+0F0h+var_C8], rax
0x1800390e4  mov     [rsp+0F0h+var_D0], rdi
0x1800390e9  call    WPP_SF_iSI
0x1800390ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390f5  cmp     rcx, r14
0x1800390f8  jz      loc_180039256
0x1800390fe  cmp     byte ptr [rcx+19h], 4
0x180039102  jb      loc_1800391A9
0x180039108  test    byte ptr [rcx+1Ch], 10h
0x18003910c  jz      loc_1800391A9
0x180039112  mov     rdx, cs:gIkeExtGlobals
0x180039119  test    rdx, rdx
0x18003911c  jz      short loc_180039144
0x18003911e  mov     eax, [rdx+0D88h]
0x180039124  cmp     eax, 0FFFFFFFFh
0x180039127  jz      short loc_180039144
0x180039129  mov     ecx, eax; dwTlsIndex
0x18003912b  call    cs:__imp_TlsGetValue
0x180039131  mov     rcx, cs:WPP_GLOBAL_Control
0x180039138  mov     r8, rax
0x18003913b  mov     rdx, cs:gIkeExtGlobals
0x180039142  jmp     short loc_180039147
0x180039144  mov     r8, rsi
0x180039147  test    r8, r8
0x18003914a  lea     rdi, [r8+8]
0x18003914e  cmovz   rdi, rsi
0x180039152  test    rdx, rdx
0x180039155  jz      short loc_18003917B
0x180039157  mov     eax, [rdx+0D88h]
0x18003915d  cmp     eax, 0FFFFFFFFh
0x180039160  jz      short loc_18003917B
0x180039162  mov     ecx, eax; dwTlsIndex
0x180039164  call    cs:__imp_TlsGetValue
0x18003916a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039171  test    rax, rax
0x180039174  jz      short loc_18003917B
0x180039176  mov     r9, [rax]
0x180039179  jmp     short loc_18003917E
0x18003917b  mov     r9, rsi
0x18003917e  mov     eax, [rbx+148h]
0x180039184  lea     r8, WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids
0x18003918b  mov     rcx, [rcx+10h]
0x18003918f  mov     edx, 1Ah
0x180039194  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180039198  mov     [rsp+0F0h+var_D0], rdi
0x18003919d  call    WPP_SF_iSL
0x1800391a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391a9  cmp     rcx, r14
0x1800391ac  jz      loc_180039256
0x1800391b2  cmp     byte ptr [rcx+19h], 4
0x1800391b6  jb      loc_180039256
0x1800391bc  test    byte ptr [rcx+1Ch], 10h
0x1800391c0  jz      loc_180039256
0x1800391c6  mov     rdx, cs:gIkeExtGlobals
0x1800391cd  test    rdx, rdx
0x1800391d0  jz      short loc_1800391F8
0x1800391d2  mov     eax, [rdx+0D88h]
0x1800391d8  cmp     eax, 0FFFFFFFFh
0x1800391db  jz      short loc_1800391F8
0x1800391dd  mov     ecx, eax; dwTlsIndex
0x1800391df  call    cs:__imp_TlsGetValue
0x1800391e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391ec  mov     r8, rax
0x1800391ef  mov     rdx, cs:gIkeExtGlobals
0x1800391f6  jmp     short loc_1800391FB
0x1800391f8  mov     r8, rsi
0x1800391fb  test    r8, r8
0x1800391fe  lea     rdi, [r8+8]
0x180039202  cmovz   rdi, rsi
0x180039206  test    rdx, rdx
0x180039209  jz      short loc_18003922F
0x18003920b  mov     eax, [rdx+0D88h]
0x180039211  cmp     eax, 0FFFFFFFFh
0x180039214  jz      short loc_18003922F
0x180039216  mov     ecx, eax; dwTlsIndex
0x180039218  call    cs:__imp_TlsGetValue
0x18003921e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039225  test    rax, rax
0x180039228  jz      short loc_18003922F
0x18003922a  mov     r9, [rax]
0x18003922d  jmp     short loc_180039232
0x18003922f  mov     r9, rsi
0x180039232  mov     eax, [rbx+178h]
0x180039238  lea     r8, WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids
0x18003923f  mov     rcx, [rcx+10h]
0x180039243  mov     edx, 1Bh
0x180039248  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18003924c  mov     [rsp+0F0h+var_D0], rdi
0x180039251  call    WPP_SF_iSL
0x180039256  mov     rdi, [rsp+0F0h+arg_8]
0x18003925e  mov     eax, cs:dword_180173278
0x180039264  mov     r14, [rsp+0F0h+arg_10]
0x18003926c  cmp     eax, 4
0x18003926f  jbe     loc_1800393EB
0x180039275  mov     rax, cs:gIkeExtGlobals
0x18003927c  test    rax, rax
0x18003927f  jz      short loc_1800392AA
0x180039281  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180039287  cmp     ecx, 0FFFFFFFFh
0x18003928a  jz      short loc_1800392AA
0x18003928c  call    cs:__imp_TlsGetValue
0x180039292  test    rax, rax
0x180039295  jz      short loc_1800392A3
0x180039297  mov     rcx, [rax]
0x18003929a  mov     rax, cs:gIkeExtGlobals
0x1800392a1  jmp     short loc_1800392AD
0x1800392a3  mov     rax, cs:gIkeExtGlobals
0x1800392aa  mov     rcx, rsi
0x1800392ad  mov     [rbp+57h+var_B0], rcx
0x1800392b1  lea     rcx, [rbp+57h+var_B0]
0x1800392b5  mov     [rbp+57h+var_70], rcx
0x1800392b9  mov     [rbp+57h+var_68], 8
0x1800392c1  test    rax, rax
0x1800392c4  jz      short loc_180039304
0x1800392c6  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800392cc  cmp     ecx, 0FFFFFFFFh
0x1800392cf  jz      short loc_180039304
0x1800392d1  call    cs:__imp_TlsGetValue
0x1800392d7  test    rax, rax
0x1800392da  lea     rdx, [rax+8]
0x1800392de  cmovz   rdx, rsi
0x1800392e2  test    rdx, rdx
0x1800392e5  jz      short loc_180039304
0x1800392e7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800392ee  xchg    ax, ax
0x1800392f0  cmp     [rdx+rax*2+2], si
0x1800392f5  lea     rax, [rax+1]
0x1800392f9  jnz     short loc_1800392F0
0x1800392fb  lea     eax, ds:2[rax*2]
0x180039302  jmp     short loc_180039310
0x180039304  lea     rdx, LocaleName
0x18003930b  mov     eax, 2
0x180039310  mov     [rbp+57h+var_58], eax
0x180039313  lea     rcx, _TraceLoggingMetadata
0x18003931a  mov     rax, [rbx+140h]
0x180039321  xor     r9d, r9d
0x180039324  mov     [rbp+57h+var_A8], rax
0x180039328  xor     r8d, r8d
0x18003932b  mov     [rbp+57h+var_60], rdx
0x18003932f  lea     rax, [rbp+57h+var_A8]
0x180039333  mov     [rbp+57h+var_50], rax
0x180039337  lea     rdx, [rbp+57h+var_A0]
0x18003933b  mov     eax, [rbx+148h]
0x180039341  mov     [rbp+57h+var_BC], eax
0x180039344  lea     rax, [rbp+57h+var_BC]
0x180039348  mov     [rbp+57h+var_40], rax
0x18003934c  mov     eax, [rbx+178h]
0x180039352  mov     [rbp+57h+var_B8], eax
0x180039355  lea     rax, [rbp+57h+var_B8]
0x180039359  mov     [rbp+57h+var_30], rax
0x18003935d  movzx   eax, cs:word_18015ADF3
0x180039364  mov     [rbp+57h+var_9C], eax
0x180039367  mov     rax, cs:off_180173280
0x18003936e  mov     [rbp+57h+var_90], rax
0x180039372  mov     [rbp+57h+var_54], esi
0x180039375  mov     [rbp+57h+var_48], 8
0x18003937d  mov     [rbp+57h+var_38], 4
0x180039385  mov     [rbp+57h+var_28], 4
0x18003938d  mov     [rbp+57h+var_A0], 0B000000h
0x180039394  mov     [rbp+57h+var_98], rsi
0x180039398  movzx   eax, word ptr [rax]
0x18003939b  mov     [rbp+57h+var_88], eax
0x18003939e  lea     rax, byte_18015ADFD
0x1800393a5  mov     [rbp+57h+var_80], rax
0x1800393a9  lea     rax, _TraceLoggingMetadataEnd
0x1800393b0  sub     eax, ecx
0x1800393b2  mov     [rbp+57h+var_84], 2
0x1800393b9  mov     [rbp+57h+var_78], 49h ; 'I'
0x1800393c0  mov     [rbp+57h+var_74], 1
0x1800393c7  mov     [rbp+57h+var_C0], eax
0x1800393ca  mov     eax, [rbp+57h+var_C0]
0x1800393cd  mov     rcx, cs:qword_180173298
0x1800393d4  lea     rax, [rbp+57h+var_90]
0x1800393d8  mov     [rsp+0F0h+var_C8], rax
0x1800393dd  mov     dword ptr [rsp+0F0h+var_D0], 7
0x1800393e5  call    cs:__imp_EtwEventWriteTransfer
0x1800393eb  mov     rcx, [rbp+57h+var_20]
0x1800393ef  xor     rcx, rsp; StackCookie
0x1800393f2  call    __security_check_cookie
0x1800393f7  add     rsp, 0E0h
0x1800393fe  pop     rsi
0x1800393ff  pop     rbx
0x180039400  pop     rbp
0x180039401  retn
```
