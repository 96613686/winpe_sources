# WSManHttpSenderConnection::CreateNewNegotiateAuthTokens(void)

- ea: `0x180062fc0`
- end: `0x180063a77`
- name: `?CreateNewNegotiateAuthTokens@WSManHttpSenderConnection@@AEAAKXZ`
- size: `2743`
- prototype: `unsigned int __fastcall(WSManHttpSenderConnection *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004bb70`
- `0x180053424`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18004a900`
- `0x180062fc0`
- `0x180063a80`
- `0x180063d68`
- `0x180065a7c`
- `0x180067150`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x18011349c`
- `0x18011a6d4`
- `0x18011d870`
- `0x1801262f4`
- `0x1801337c4`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063052`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006324f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063052`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006324f`
- `SspiCli!InitializeSecurityContextW` at `0x18006317a`
- `SspiCli!InitializeSecurityContextW` at `0x18006317a`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800633e1`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800633e1`

## string_xrefs

- `0x1800635ee`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x1800639de`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18006395a`: `SEC_I_COMPLETE_AND_CONTINUE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WSManHttpSenderConnection::CreateNewNegotiateAuthTokens(WSManHttpSenderConnection *this)
{
  WSManHttpSenderConnection *v1; // r15
  PVOID *v2; // rcx
  LPVOID v3; // rax
  struct _SecBufferDesc *pInput; // rsi
  int v5; // ebx
  unsigned int v6; // r8d
  __int64 v7; // rax
  unsigned int v8; // r9d
  __int64 v9; // rcx
  PVOID *v10; // r10
  int v11; // edx
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  unsigned int v15; // edi
  struct _SecHandle *v16; // rdx
  SECURITY_STATUS v17; // eax
  PVOID *v18; // rcx
  CHeap *v19; // rcx
  int v20; // edi
  int v21; // eax
  char **v22; // rbx
  __int64 *v23; // rax
  char *v24; // rbx
  CHeap *v25; // rcx
  unsigned int v26; // r14d
  __int64 v27; // rdi
  unsigned int v28; // r13d
  void *Handle; // rax
  const WCHAR *v30; // r12
  __int64 v31; // r15
  __int64 v32; // r13
  __int64 v33; // rax
  __int64 v34; // rcx
  WCHAR *v35; // rdx
  char v36; // r8
  WCHAR *v37; // rax
  int v38; // ebx
  __int64 v39; // rcx
  const WCHAR *v40; // rax
  __int64 v41; // rax
  const char *v42; // rcx
  __int64 v43; // r15
  char *i; // rdx
  char v45; // al
  char *v46; // rax
  __int64 v47; // r8
  __int64 v48; // r10
  __int64 v49; // rdx
  bool v50; // zf
  __int64 v51; // r9
  const unsigned __int16 *v53; // r8
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rax
  const wchar_t *v60; // r9
  int v61; // eax
  const wchar_t *v62; // r9
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v64; // [rsp+68h] [rbp-98h] BYREF
  WSManHttpSenderConnection *v65; // [rsp+70h] [rbp-90h]
  __int128 v66; // [rsp+78h] [rbp-88h] BYREF
  __int128 v67; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v68; // [rsp+98h] [rbp-68h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v70; // [rsp+B0h] [rbp-50h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v72[12]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = this;
  v65 = this;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      222,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      v1,
      *((_QWORD *)v1 + 1));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  pOutput = 0;
  v67 = 0;
  v66 = 0;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  v64 = 0;
  if ( dword_18027FBEC == 2 )
  {
    if ( g_wsManHeap )
    {
      v3 = HeapAlloc(g_wsManHeap, 0, *((unsigned int *)v1 + 2086));
      goto LABEL_5;
    }
  }
  else
  {
    if ( dword_18027FBEC == 4 )
    {
      if ( v2 == &WPP_GLOBAL_Control || (*((_DWORD *)v2 + 7) & 0x40000000) == 0 )
        goto LABEL_92;
      v55 = 10;
    }
    else if ( dword_18027FBEC == 8 )
    {
      if ( v2 == &WPP_GLOBAL_Control || (*((_DWORD *)v2 + 7) & 0x40000000) == 0 )
        goto LABEL_92;
      v55 = 11;
    }
    else
    {
      if ( v2 == &WPP_GLOBAL_Control || (*((_DWORD *)v2 + 7) & 0x40000000) == 0 )
        goto LABEL_92;
      v55 = 12;
    }
    WPP_SF_(v2[2], v55, WPP_9bd13fd0c4ba3d813d171a602a744429_Traceguids);
  }
LABEL_92:
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  v3 = 0;
LABEL_5:
  v68 = v3;
  if ( v3 )
  {
    pInput = 0;
    pOutput.ulVersion = 0;
    v5 = 1;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)&v67;
    DWORD1(v67) = 2;
    *((_QWORD *)&v67 + 1) = v3;
    LODWORD(v67) = *((_DWORD *)v1 + 2086);
    *(_QWORD *)&v66 = 0;
    v6 = 0;
    *((_QWORD *)&v66 + 1) = v72;
    if ( *((_QWORD *)v1 + 1126) )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        v6 = DWORD1(v66);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      v56 = 2LL * v6;
      v72[2 * v56 + 1] = 14;
      v57 = *((_QWORD *)v1 + 1126);
      *(_QWORD *)&v72[2 * v56 + 2] = *(_QWORD *)(v57 + 8);
      v72[2 * v56] = *(_DWORD *)v57;
      DWORD1(v66) = ++v6;
      v7 = v6;
      v9 = v6;
      v8 = v6;
    }
    else
    {
      v7 = 0;
      v8 = 0;
      v9 = 0;
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = *((_DWORD *)v1 + 2232);
    if ( v11 )
    {
      v72[4 * v7 + 1] = 2;
      v58 = 2 * v9;
      v72[2 * v58] = v11;
      *(_QWORD *)&v72[2 * v58 + 2] = *((_QWORD *)v1 + 1115);
      DWORD1(v66) = v8 + 1;
      if ( (unsigned int)WSManHttpSenderConnection::GetNegotiationAuthMode(v1) == 2 )
      {
        v72[4 * v6 + 1] = 0;
        v59 = 2LL * v6;
        v72[2 * v59] = 0;
        *(_QWORD *)&v72[2 * v59 + 2] = 0;
        DWORD1(v66) = ++v6;
      }
    }
    else if ( *((_QWORD *)v1 + 1041) != -1
           && *((_QWORD *)v1 + 1042) != -1
           && v10 != &WPP_GLOBAL_Control
           && (*((_DWORD *)v10 + 7) & 0x400) != 0 )
    {
      WPP_SF_(v10[2], 224, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
      v6 = DWORD1(v66);
    }
    v12 = *((_DWORD *)v1 + 2848);
    if ( v12 == 5 )
      goto LABEL_62;
    v13 = *((_DWORD *)v1 + 2849);
    if ( v13 == 4 )
    {
LABEL_12:
      v14 = 1;
      goto LABEL_13;
    }
    if ( v13 == 5 )
    {
LABEL_62:
      v14 = 0;
    }
    else
    {
      if ( v12 == 4 )
        goto LABEL_12;
      v14 = (v12 != 7) + 2;
    }
LABEL_13:
    if ( v14 != 2 )
      v5 = 3;
    v15 = v5 | 0x14;
    if ( *((_BYTE *)v1 + 48) )
      v15 = v5;
    if ( v6 )
      pInput = (struct _SecBufferDesc *)&v66;
    if ( *((_QWORD *)v1 + 1041) == -1 || (v16 = (struct _SecHandle *)((char *)v1 + 8328), *((_QWORD *)v1 + 1042) == -1) )
      v16 = 0;
    v17 = InitializeSecurityContextW(
            (PCredHandle)((char *)v1 + 8312),
            v16,
            *((SEC_WCHAR **)v1 + 1114),
            v15,
            0,
            0x10u,
            pInput,
            0,
            (PCtxtHandle)((char *)v1 + 8328),
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
    LODWORD(pInput) = v17;
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        if ( *((_QWORD *)v1 + 1041) == -1 || (v60 = L"continuation", *((_QWORD *)v1 + 1042) == -1) )
          v60 = L"new context";
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          226,
          (unsigned int)&WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          (_DWORD)v60,
          v17);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v18 + 7) & 0x400) != 0 )
        {
          WPP_SF_d(v18[2], 227, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v15);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x400) != 0 )
        {
          WPP_SF_d(v18[2], 228, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, pfContextAttr);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    if ( (int)pInput < 0 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x200) != 0 )
        WPP_SF_dq(v18[2], 229, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, (unsigned int)pInput, v1);
      WSManHttpSenderConnection::RecordSecurityContextFailure(v1, (int)pInput);
      goto LABEL_67;
    }
    if ( (((_DWORD)pInput - 590610) & 0xFFFFFFFD) == 0 )
    {
      *((_BYTE *)v1 + 8254) = 0;
      *((_BYTE *)v1 + 9017) = 1;
      v19 = (CHeap *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v62 = L"SEC_I_CONTINUE_NEEDED";
        if ( (_DWORD)pInput != 590610 )
          v62 = L"SEC_I_COMPLETE_AND_CONTINUE";
        WPP_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          230,
          (unsigned int)&WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
          (_DWORD)v62,
          (char)v1);
      }
LABEL_27:
      v20 = v67;
      v21 = *((_DWORD *)v1 + 2848);
      if ( v21 == 5 )
        goto LABEL_64;
      v19 = (CHeap *)*((unsigned int *)v1 + 2849);
      if ( (_DWORD)v19 == 4 )
      {
LABEL_29:
        v22 = &off_18027B140;
        v23 = &qword_18027B148;
        goto LABEL_30;
      }
      if ( (_DWORD)v19 == 5 )
      {
LABEL_64:
        v22 = &off_18027B0C8;
        v23 = &qword_18027B0D0;
      }
      else
      {
        if ( v21 == 4 )
          goto LABEL_29;
        if ( v21 == 7 )
        {
          v22 = &off_18027B1B8;
          v23 = &qword_18027B1C0;
        }
        else
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
            4316,
            L"4316",
            0x54Fu,
            0);
          v22 = (char **)&qword_18027B230;
          v23 = qword_18027B238;
        }
      }
LABEL_30:
      v24 = *v22;
      pInput = (struct _SecBufferDesc *)*(unsigned int *)v23;
      if ( CHeap::GetHandle(v19) )
      {
        v25 = (CHeap *)(unsigned int)(v20 + 2);
        v26 = 4 * ((unsigned int)v25 / 3);
        v27 = (unsigned int)pInput + v26;
        v28 = v27 + 3;
        Handle = CHeap::GetHandle(v25);
        v30 = (const WCHAR *)HeapAlloc(Handle, 0, (unsigned int)(2 * (v27 + 3)));
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
        v64 = v30;
        if ( v30 )
        {
          v31 = v28;
          if ( (_DWORD)v27 == -3 )
          {
            v38 = -2147024809;
          }
          else if ( v28 > 0x7FFFFFFFuLL )
          {
            v38 = -2147024809;
            *(_BYTE *)v30 = 0;
          }
          else
          {
            v32 = 2147483646;
            v33 = 2147483646;
            v34 = (unsigned int)v31;
            v35 = (WCHAR *)v30;
            do
            {
              if ( !v33 )
                break;
              v36 = *v24;
              if ( !*v24 )
                break;
              ++v24;
              *(_BYTE *)v35 = v36;
              v35 = (WCHAR *)((char *)v35 + 1);
              --v33;
              --v34;
            }
            while ( v34 );
            v37 = (WCHAR *)((char *)v35 - 1);
            if ( v34 )
              v37 = v35;
            *(_BYTE *)v37 = 0;
            v38 = -2147024774;
            if ( v34 )
            {
              LODWORD(pInput) = BinaryToBase64Template<unsigned char,&unsigned char near * BinaryToBase64Table>(
                                  *((__int64 *)&v67 + 1),
                                  v67,
                                  (_BYTE *)pInput + (_QWORD)v30,
                                  v26,
                                  &v70);
              if ( (_DWORD)pInput )
              {
                v1 = v65;
                WSManError(
                  (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
                  4343,
                  L"4343",
                  0x54Fu,
                  *((struct IRequestContext **)v65 + 1128));
                goto LABEL_137;
              }
              *((_BYTE *)v30 + v27) = 0;
              v39 = v31;
              v40 = v30;
              do
              {
                if ( !*(_BYTE *)v40 )
                  break;
                v40 = (const WCHAR *)((char *)v40 + 1);
                --v39;
              }
              while ( v39 );
              v38 = -2147024809;
              if ( v39 )
              {
                v41 = v31 - v39;
                v42 = "\r\n";
                v43 = v31 - v41;
                for ( i = (char *)v30 + v41; v43; --v43 )
                {
                  if ( !v32 )
                    break;
                  v45 = *v42;
                  if ( !*v42 )
                    break;
                  ++v42;
                  *i++ = v45;
                  --v32;
                }
                v38 = -2147024774;
                if ( v43 )
                  v38 = 0;
                v46 = i - 1;
                if ( v43 )
                  v46 = i;
                *v46 = 0;
                if ( v43 )
                {
                  v47 = (unsigned int)(v27 + 2);
                  LODWORD(v48) = v47;
                  v49 = (unsigned int)(2 * v47);
                  *((_BYTE *)v30 + v49) = *((_BYTE *)v30 + v47);
                  *((_BYTE *)v30 + (unsigned int)(v49 + 1)) = 0;
                  if ( (_DWORD)v27 != -2 )
                  {
                    do
                    {
                      v50 = (_DWORD)v48 == 1;
                      v48 = (unsigned int)(v48 - 1);
                      v51 = (unsigned int)(2 * v48);
                      *((_BYTE *)v30 + v51) = *((_BYTE *)v30 + v48);
                      *((_BYTE *)v30 + (unsigned int)(v51 + 1)) = 0;
                    }
                    while ( !v50 );
                  }
                  v1 = v65;
                  if ( WinHttpAddRequestHeaders(*((HINTERNET *)v65 + 1134), v30, v47, 0xA0000000) )
                    goto LABEL_68;
                  pInput = (struct _SecBufferDesc *)GetLastError();
                  (*(void (__fastcall **)(_QWORD, struct _SecBufferDesc *))(**((_QWORD **)v1 + 1128) + 72LL))(
                    *((_QWORD *)v1 + 1128),
                    pInput);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      233,
                      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
                      (unsigned int)pInput);
LABEL_67:
                  if ( !(_DWORD)pInput )
                  {
LABEL_68:
                    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v68);
                    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
                    return (unsigned int)pInput;
                  }
LABEL_137:
                  WSManHttpSenderConnection::ResetNegotiationContext(v1);
                  goto LABEL_68;
                }
              }
              v53 = L"4350";
              v54 = 4350;
LABEL_77:
              v1 = v65;
              WSManError(
                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
                v54,
                v53,
                0x54Fu,
                *((struct IRequestContext **)v65 + 1128));
              LODWORD(pInput) = (unsigned __int16)v38;
              if ( (v38 & 0x1FFF0000) != 0x70000 )
                LODWORD(pInput) = v38;
              goto LABEL_67;
            }
          }
          v53 = L"4336";
          v54 = 4336;
          goto LABEL_77;
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
        v64 = 0;
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 1128) + 24LL))(*((_QWORD *)v1 + 1128));
      LODWORD(pInput) = 14;
      goto LABEL_137;
    }
    v61 = WSManHttpSenderConnection::ValidateContextRequirements(v1, pfContextAttr);
    if ( (_DWORD)pInput == 590611 )
    {
      if ( v61 )
      {
        *((_BYTE *)v1 + 8254) = 1;
        *((_BYTE *)v1 + 9017) = 1;
        v19 = (CHeap *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        goto LABEL_27;
      }
    }
    else if ( v61 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v1);
      *((_DWORD *)v1 + 2074) = 0;
      *((_BYTE *)v1 + 9017) = 0;
      *((_BYTE *)v1 + 8254) = 1;
      if ( (unsigned int)WSManHttpSenderConnection::GetNegotiationAuthMode(v1) != 2
        && (pfContextAttr & v15 & 0xFFFFFFFE) != (v15 & 0xFFFFFFFE) )
      {
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
          4306,
          L"4306",
          0x54Fu,
          0);
      }
      goto LABEL_27;
    }
    LODWORD(pInput) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 1128) + 152LL))(*((_QWORD *)v1 + 1128));
    goto LABEL_67;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 1128) + 24LL))(*((_QWORD *)v1 + 1128));
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v68);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
  return 14;
}

```

## disassembly

```asm
0x180062fc0  push    rbp
0x180062fc2  push    rbx
0x180062fc3  push    rsi
0x180062fc4  push    rdi
0x180062fc5  push    r12
0x180062fc7  push    r13
0x180062fc9  push    r14
0x180062fcb  push    r15
0x180062fcd  lea     rbp, [rsp-8]
0x180062fd2  sub     rsp, 108h
0x180062fd9  mov     rax, cs:__security_cookie
0x180062fe0  xor     rax, rsp
0x180062fe3  mov     [rbp+40h+var_50], rax
0x180062fe7  mov     r15, rcx
0x180062fea  mov     [rsp+140h+var_D0], rcx
0x180062fef  lea     r12, WPP_GLOBAL_Control
0x180062ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ffd  cmp     rcx, r12
0x180063000  jnz     loc_1800634C1
0x180063006  xorps   xmm0, xmm0
0x180063009  movups  xmmword ptr [rbp+40h+var_A0.ulVersion], xmm0
0x18006300d  xorps   xmm1, xmm1
0x180063010  movups  [rbp+40h+var_B8], xmm1
0x180063014  movups  [rsp+140h+var_C8], xmm0
0x180063019  xor     r14d, r14d
0x18006301c  mov     [rsp+140h+var_E0], r14d
0x180063021  mov     qword ptr [rbp+40h+var_88], r14
0x180063025  mov     [rsp+140h+var_D8], r14
0x18006302a  mov     eax, cs:dword_18027FBEC
0x180063030  cmp     eax, 2
0x180063033  jnz     loc_180063580
0x180063039  mov     rcx, cs:?g_wsManHeap@@3VCHeap@@A; hHeap
0x180063040  test    rcx, rcx
0x180063043  jz      loc_1800635D7
0x180063049  mov     r8d, [r15+2098h]; dwBytes
0x180063050  xor     edx, edx; dwFlags
0x180063052  call    cs:__imp_HeapAlloc
0x180063058  mov     [rbp+40h+var_A8], rax
0x18006305c  test    rax, rax
0x18006305f  jz      loc_180063602
0x180063065  mov     rsi, r14
0x180063068  mov     [rbp+40h+var_A0.ulVersion], r14d
0x18006306c  mov     ebx, 1
0x180063071  mov     [rbp+40h+var_A0.cBuffers], ebx
0x180063074  lea     rcx, [rbp+40h+var_B8]
0x180063078  mov     [rbp+40h+var_A0.pBuffers], rcx
0x18006307c  mov     dword ptr [rbp+40h+var_B8+4], 2
0x180063083  mov     qword ptr [rbp+40h+var_B8+8], rax
0x180063087  mov     eax, [r15+2098h]
0x18006308e  mov     dword ptr [rbp+40h+var_B8], eax
0x180063091  mov     qword ptr [rsp+140h+var_C8], r14
0x180063096  mov     r8d, r14d
0x180063099  lea     rax, [rbp+40h+var_80]
0x18006309d  mov     qword ptr [rbp+40h+var_C8+8], rax
0x1800630a1  cmp     [r15+2330h], r14
0x1800630a8  jnz     loc_180063634
0x1800630ae  mov     eax, r14d
0x1800630b1  mov     r9d, r14d
0x1800630b4  mov     ecx, r14d
0x1800630b7  mov     r10, cs:WPP_GLOBAL_Control
0x1800630be  mov     edx, [r15+22E0h]
0x1800630c5  test    edx, edx
0x1800630c7  jnz     loc_1800636A5
0x1800630cd  cmp     qword ptr [r15+2088h], 0FFFFFFFFFFFFFFFFh
0x1800630d5  jnz     loc_180063705
0x1800630db  mov     eax, [r15+2C80h]
0x1800630e2  cmp     eax, 5
0x1800630e5  jz      loc_18006344C
0x1800630eb  mov     ecx, [r15+2C84h]
0x1800630f2  cmp     ecx, 4
0x1800630f5  jnz     loc_180063443
0x1800630fb  mov     ecx, ebx
0x1800630fd  mov     eax, 3
0x180063102  cmp     ecx, 2
0x180063105  cmovnz  ebx, eax
0x180063108  mov     edi, ebx
0x18006310a  or      edi, 14h
0x18006310d  cmp     [r15+30h], sil
0x180063111  cmovnz  edi, ebx
0x180063114  test    r8d, r8d
0x180063117  jnz     loc_180063749
0x18006311d  lea     rbx, [r15+2088h]
0x180063124  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180063128  jnz     loc_180063753
0x18006312e  mov     rdx, r14; phContext
0x180063131  lea     rcx, [r15+2078h]; phCredential
0x180063138  lea     rax, [rbp+40h+var_88]
0x18006313c  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x180063141  lea     rax, [rsp+140h+var_E0]
0x180063146  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x18006314b  lea     rax, [rbp+40h+var_A0]
0x18006314f  mov     [rsp+140h+pOutput], rax; pOutput
0x180063154  mov     [rsp+140h+phNewContext], rbx; phNewContext
0x180063159  mov     [rsp+140h+Reserved2], r14d; Reserved2
0x18006315e  mov     [rsp+140h+pInput], rsi; pInput
0x180063163  mov     [rsp+140h+TargetDataRep], 10h; TargetDataRep
0x18006316b  mov     [rsp+140h+Reserved1], r14d; Reserved1
0x180063170  mov     r9d, edi; fContextReq
0x180063173  mov     r8, [r15+22D0h]; pszTargetName
0x18006317a  call    cs:__imp_InitializeSecurityContextW
0x180063180  mov     esi, eax
0x180063182  mov     rcx, cs:WPP_GLOBAL_Control
0x180063189  cmp     rcx, r12
0x18006318c  jz      short loc_1800631A4
0x18006318e  test    dword ptr [rcx+1Ch], 400h
0x180063195  jnz     loc_180063769
0x18006319b  cmp     rcx, r12
0x18006319e  jnz     loc_1800637AC
0x1800631a4  test    esi, esi
0x1800631a6  js      loc_180063470
0x1800631ac  lea     eax, [rsi-90312h]
0x1800631b2  test    eax, 0FFFFFFFDh
0x1800631b7  jnz     loc_18006383F
0x1800631bd  mov     byte ptr [r15+203Eh], 0
0x1800631c5  mov     byte ptr [r15+2339h], 1
0x1800631cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800631d4  cmp     rcx, r12
0x1800631d7  jnz     loc_18006394D
0x1800631dd  mov     edi, dword ptr [rbp+40h+var_B8]
0x1800631e0  mov     eax, [r15+2C80h]
0x1800631e7  cmp     eax, 5
0x1800631ea  jz      loc_18006345D
0x1800631f0  mov     ecx, [r15+2C84h]; this
0x1800631f7  cmp     ecx, 4
0x1800631fa  jnz     loc_180063454
0x180063200  lea     rbx, off_18027B140; "Authorization: Negotiate "
0x180063207  lea     rax, qword_18027B148
0x18006320e  mov     rbx, [rbx]
0x180063211  mov     esi, [rax]
0x180063213  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180063218  test    rax, rax
0x18006321b  jz      loc_1800639C7
0x180063221  lea     ecx, [rdi+2]; this
0x180063224  mov     eax, 0AAAAAAABh
0x180063229  mul     ecx
0x18006322b  shr     edx, 1
0x18006322d  lea     r14d, ds:0[rdx*4]
0x180063235  lea     edi, [rsi+r14]
0x180063239  lea     r13d, [rdi+3]
0x18006323d  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180063242  lea     r8d, ds:0[r13*2]; dwBytes
0x18006324a  xor     edx, edx; dwFlags
0x18006324c  mov     rcx, rax; hHeap
0x18006324f  call    cs:__imp_HeapAlloc
0x180063255  mov     r12, rax
0x180063258  lea     rcx, [rsp+140h+var_D8]
0x18006325d  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180063262  mov     [rsp+140h+var_D8], r12
0x180063267  test    r12, r12
0x18006326a  jz      loc_1800639F9
0x180063270  mov     r15d, r13d
0x180063273  test    r13d, r13d
0x180063276  jz      loc_180063A56
0x18006327c  cmp     r15, 7FFFFFFFh
0x180063283  ja      loc_180063A1E
0x180063289  mov     r13d, 7FFFFFFEh
0x18006328f  mov     eax, r13d
0x180063292  mov     ecx, r15d
0x180063295  mov     rdx, r12
0x180063298  test    rax, rax
0x18006329b  jz      short loc_1800632B8
0x18006329d  movzx   r8d, byte ptr [rbx]
0x1800632a1  test    r8b, r8b
0x1800632a4  jz      short loc_1800632B8
0x1800632a6  inc     rbx
0x1800632a9  mov     [rdx], r8b
0x1800632ac  inc     rdx
0x1800632af  dec     rax
0x1800632b2  sub     rcx, 1
0x1800632b6  jnz     short loc_180063298
0x1800632b8  lea     rax, [rdx-1]
0x1800632bc  test    rcx, rcx
0x1800632bf  cmovnz  rax, rdx
0x1800632c3  mov     byte ptr [rax], 0
0x1800632c6  mov     ebx, 8007007Ah
0x1800632cb  xor     eax, eax
0x1800632cd  test    rcx, rcx
0x1800632d0  cmovnz  ebx, eax
0x1800632d3  jz      loc_180063A65
0x1800632d9  lea     r8, [r12+rsi]
0x1800632dd  lea     rax, [rbp+40h+var_90]
0x1800632e1  mov     qword ptr [rsp+140h+Reserved1], rax
0x1800632e6  mov     r9d, r14d
0x1800632e9  mov     edx, dword ptr [rbp+40h+var_B8]
0x1800632ec  mov     rcx, qword ptr [rbp+40h+var_B8+8]
0x1800632f0  call    ??$BinaryToBase64Template@E$1?BinaryToBase64Table@@3PAEA@@YAKPEAEK0KPEAK@Z; BinaryToBase64Template<uchar,&uchar near * BinaryToBase64Table>(uchar *,ulong,uchar *,ulong,ulong *)
0x1800632f5  mov     esi, eax
0x1800632f7  test    eax, eax
0x1800632f9  jnz     loc_180063A25
0x1800632ff  mov     [rdi+r12], al
0x180063303  mov     rcx, r15
0x180063306  mov     rax, r12
0x180063309  nop     dword ptr [rax+00000000h]
0x180063310  cmp     byte ptr [rax], 0
0x180063313  jz      short loc_18006331E
0x180063315  inc     rax
0x180063318  sub     rcx, 1
0x18006331c  jnz     short loc_180063310
0x18006331e  mov     ebx, 80070057h
0x180063323  xor     eax, eax
0x180063325  test    rcx, rcx
0x180063328  cmovnz  ebx, eax
0x18006332b  jz      loc_18006353A
0x180063331  mov     rax, r15
0x180063334  sub     rax, rcx
0x180063337  test    rcx, rcx
0x18006333a  jz      loc_18006353A
0x180063340  lea     rcx, asc_1801D51CC; "\r\n"
0x180063347  sub     r15, rax
0x18006334a  lea     rdx, [rax+r12]
0x18006334e  jz      short loc_18006336D
0x180063350  test    r13, r13
0x180063353  jz      short loc_18006336D
0x180063355  movzx   eax, byte ptr [rcx]
0x180063358  test    al, al
0x18006335a  jz      short loc_18006336D
0x18006335c  inc     rcx
0x18006335f  mov     [rdx], al
0x180063361  inc     rdx
0x180063364  dec     r13
0x180063367  sub     r15, 1
0x18006336b  jnz     short loc_180063350
0x18006336d  xor     eax, eax
0x18006336f  test    r15, r15
0x180063372  mov     ebx, 8007007Ah
0x180063377  cmovnz  ebx, eax
0x18006337a  lea     rax, [rdx-1]
0x18006337e  cmovnz  rax, rdx
0x180063382  mov     byte ptr [rax], 0
0x180063385  jz      loc_18006353A
0x18006338b  lea     r8d, [rdi+3]
0x18006338f  sub     r8d, 1; dwHeadersLength
0x180063393  mov     r10d, r8d
0x180063396  lea     edx, [r8+r8]
0x18006339a  movzx   eax, byte ptr [r8+r12]
0x18006339f  mov     [rdx+r12], al
0x1800633a3  lea     eax, [rdx+1]
0x1800633a6  mov     byte ptr [rax+r12], 0
0x1800633ab  jz      short loc_1800633CC
0x1800633ad  nop     dword ptr [rax]
0x1800633b0  add     r10d, 0FFFFFFFFh
0x1800633b4  lea     r9d, [r10+r10]
0x1800633b8  movzx   eax, byte ptr [r10+r12]
0x1800633bd  mov     [r9+r12], al
0x1800633c1  lea     eax, [r9+1]
0x1800633c5  mov     byte ptr [rax+r12], 0
0x1800633ca  jnz     short loc_1800633B0
0x1800633cc  mov     r15, [rsp+140h+var_D0]
0x1800633d1  mov     rcx, [r15+2370h]; hRequest
0x1800633d8  mov     r9d, 0A0000000h; dwModifiers
0x1800633de  mov     rdx, r12; lpszHeaders
0x1800633e1  call    cs:__imp_WinHttpAddRequestHeaders
0x1800633e7  cmp     eax, 1
0x1800633ea  jz      loc_18006348B
0x1800633f0  call    cs:__imp_GetLastError
0x1800633f6  mov     esi, eax
0x1800633f8  mov     rcx, [r15+2340h]
0x1800633ff  mov     rax, [rcx]
0x180063402  mov     edx, esi
0x180063404  mov     rax, [rax+48h]
0x180063408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006340d  mov     rcx, cs:WPP_GLOBAL_Control
0x180063414  lea     rax, WPP_GLOBAL_Control
0x18006341b  cmp     rcx, rax
0x18006341e  jz      short loc_180063483
0x180063420  test    dword ptr [rcx+1Ch], 200h
0x180063427  jz      short loc_180063483
0x180063429  mov     edx, 0E9h
0x18006342e  mov     r9d, esi
0x180063431  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x180063438  mov     rcx, [rcx+10h]
0x18006343c  call    WPP_SF_d
0x180063441  jmp     short loc_180063483
0x180063443  cmp     ecx, 5
0x180063446  jnz     loc_1800634FB
0x18006344c  mov     ecx, r14d
0x18006344f  jmp     loc_1800630FD
0x180063454  cmp     ecx, 5
0x180063457  jnz     loc_180063515
0x18006345d  lea     rbx, off_18027B0C8; "Authorization: Kerberos "
0x180063464  lea     rax, qword_18027B0D0
0x18006346b  jmp     loc_18006320E
0x180063470  cmp     rcx, r12
0x180063473  jnz     loc_180063810
0x180063479  mov     edx, esi; int
0x18006347b  mov     rcx, r15; this
0x18006347e  call    ?RecordSecurityContextFailure@WSManHttpSenderConnection@@AEAAXJ@Z; WSManHttpSenderConnection::RecordSecurityContextFailure(long)
0x180063483  test    esi, esi
0x180063485  jnz     loc_180063A11
0x18006348b  lea     rcx, [rbp+40h+var_A8]
0x18006348f  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180063494  nop
0x180063495  lea     rcx, [rsp+140h+var_D8]
0x18006349a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18006349f  mov     eax, esi
0x1800634a1  mov     rcx, [rbp+40h+var_50]
0x1800634a5  xor     rcx, rsp; StackCookie
0x1800634a8  call    __security_check_cookie
0x1800634ad  add     rsp, 108h
0x1800634b4  pop     r15
  ... truncated ...
```
