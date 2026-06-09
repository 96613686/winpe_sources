# BipGetTaskInfo

- ea: `0x180053db0`
- end: `0x180054424`
- name: `BipGetTaskInfo`
- size: `1652`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, __int64, PCWSTR packageRelativeApplicationId, __int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005df20`
- `0x180081df0`

## callees

- `0x18002d280`
- `0x180038cf0`
- `0x180053db0`
- `0x18006a8d4`
- `0x18009467a`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180054086`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800541b9`
- `ntdll!RtlReleaseSRWLockShared` at `0x180054086`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800541b9`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005404c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005404c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180054240`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180054240`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180053fc7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180053fc7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005422c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005422c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800543f3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800543f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005402f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005402f`
- `OLEAUT32!__imp_SysAllocString` at `0x180053fa6`
- `OLEAUT32!__imp_SysAllocString` at `0x180053fa6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053ec3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053ef2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053f36`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053ec3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053ef2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053f36`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f53`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f5c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005420c`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f53`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f5c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005420c`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180054185`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180054185`
- `api-ms-win-appmodel-runtime-l1-1-1!FormatApplicationUserModelId` at `0x180053f89`
- `api-ms-win-appmodel-runtime-l1-1-1!FormatApplicationUserModelId` at `0x180053f89`

## string_xrefs

- `0x180053f2f`: `Windows.BackgroundTasks`

## pseudocode

```c
__int64 __fastcall BipGetTaskInfo(
        void *a1,
        __int64 ActivationContext,
        OLECHAR *a3,
        unsigned int a4,
        OLECHAR *a5,
        UINT32 a6,
        __int64 a7,
        WCHAR *packageRelativeApplicationId,
        __int64 a9,
        int a10,
        __int64 a11,
        signed int *a12)
{
  OLECHAR *v12; // r12
  WCHAR *v14; // rdi
  __int64 v16; // r13
  signed int v17; // esi
  UINT32 v18; // edi
  NTSTATUS v19; // ebx
  OLECHAR *v20; // r14
  const OLECHAR *v21; // rbx
  __int64 v22; // rcx
  _WORD *v23; // rax
  unsigned int v24; // edx
  const OLECHAR *v25; // rcx
  UINT32 v26; // edx
  OLECHAR *v27; // r12
  int v28; // ebx
  _DWORD *v29; // rdi
  PSID v30; // rcx
  unsigned int SessionIdBySid; // eax
  int v32; // ebx
  _DWORD *v33; // rbx
  int v34; // eax
  const WCHAR *v35; // rcx
  int v36; // ebx
  signed int v37; // eax
  __int64 *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rcx
  bool v41; // zf
  int v42; // ecx
  __int64 *v43; // rcx
  int v44; // eax
  int v45; // eax
  char v47; // [rsp+50h] [rbp-B0h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+54h] [rbp-ACh] BYREF
  OLECHAR *strIn; // [rsp+58h] [rbp-A8h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+68h] [rbp-98h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v53; // [rsp+78h] [rbp-88h] BYREF
  BSTR v54; // [rsp+80h] [rbp-80h]
  PSID Sid2; // [rsp+88h] [rbp-78h]
  signed int *v56; // [rsp+90h] [rbp-70h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B0h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR packageFamilyName; // [rsp+C0h] [rbp-40h] BYREF
  void *v61; // [rsp+D0h] [rbp-30h]
  int v62; // [rsp+D8h] [rbp-28h]
  int v63; // [rsp+DCh] [rbp-24h]
  __int64 *v64; // [rsp+E0h] [rbp-20h]
  int v65; // [rsp+E8h] [rbp-18h]
  int v66; // [rsp+ECh] [rbp-14h]
  __int64 *v67; // [rsp+F0h] [rbp-10h]
  int v68; // [rsp+F8h] [rbp-8h]
  int v69; // [rsp+FCh] [rbp-4h]
  OLECHAR *v70; // [rsp+100h] [rbp+0h]
  int v71; // [rsp+108h] [rbp+8h]
  int v72; // [rsp+10Ch] [rbp+Ch]
  BSTR *p_bstrString; // [rsp+110h] [rbp+10h]
  __int64 v74; // [rsp+118h] [rbp+18h]
  UINT32 *p_packageRelativeApplicationIdLength; // [rsp+120h] [rbp+20h]
  __int64 v76; // [rsp+128h] [rbp+28h]
  UINT32 *v77; // [rsp+130h] [rbp+30h]
  __int64 v78; // [rsp+138h] [rbp+38h]
  WCHAR applicationUserModelId[136]; // [rsp+150h] [rbp+50h] BYREF

  v12 = a3;
  v14 = packageRelativeApplicationId;
  bstrString = a5;
  packageRelativeApplicationIdLength = a6;
  v59 = a9;
  v58 = a11;
  v56 = a12;
  v47 = 0;
  strIn = a3;
  v16 = 0;
  Sid2 = a1;
  v53 = 0;
  v17 = 0;
  applicationUserModelIdLength = 0;
  *(_QWORD *)&EventDescriptor.Id = a7;
  *(_QWORD *)packageFamilyNameLength = packageRelativeApplicationId;
  memset_0(applicationUserModelId, 0, 0x104u);
  if ( !g_BiActInitialized )
  {
    v18 = 1000;
    v19 = -1073741729;
    LOBYTE(v20) = 0;
    goto LABEL_50;
  }
  v21 = (const OLECHAR *)(a7 + 256);
  if ( a7 == -256 )
    goto LABEL_9;
  v22 = 65;
  v23 = (_WORD *)(a7 + 256);
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v22;
  }
  while ( v22 );
  if ( !v22 )
LABEL_9:
    v24 = 0;
  else
    v24 = 2 * (65 - v22);
  v54 = SysAllocStringLen(v21, v24 >> 1);
  if ( v54 )
  {
    v20 = SysAllocStringLen(strIn, a4 >> 1);
    if ( !v20 )
    {
      v18 = 3000;
      v19 = -1073741801;
      SysFreeString(v54);
      goto LABEL_49;
    }
    v25 = bstrString;
    if ( bstrString )
    {
      v26 = packageRelativeApplicationIdLength >> 1;
    }
    else
    {
      v26 = 23;
      v25 = L"Windows.BackgroundTasks";
    }
    bstrString = SysAllocStringLen(v25, v26);
    if ( !bstrString )
    {
      v18 = 4000;
      v19 = -1073741801;
      SysFreeString(v20);
      SysFreeString(v54);
      LOBYTE(v20) = 0;
      goto LABEL_49;
    }
    v27 = 0;
    if ( *packageRelativeApplicationId )
    {
      applicationUserModelIdLength = 130;
      if ( FormatApplicationUserModelId(
             v21,
             packageRelativeApplicationId,
             &applicationUserModelIdLength,
             applicationUserModelId) )
      {
        v18 = 5000;
        v19 = -1073741823;
        goto LABEL_47;
      }
      v27 = SysAllocString(applicationUserModelId);
      if ( !v27 )
      {
        v18 = 5500;
        v19 = -1073741801;
        goto LABEL_47;
      }
    }
    v17 = CoInitializeEx(0, 0);
    if ( v17 < 0 )
    {
      v18 = 6000;
      v19 = -1073741823;
      goto LABEL_47;
    }
    v47 = 1;
    if ( ActivationContext )
    {
      v16 = ActivationContext;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)ActivationContext + 8LL))(ActivationContext);
      goto LABEL_34;
    }
    v28 = 1 << dword_1800C46D8;
    v29 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
    if ( *v29 >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
      BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
    RtlAcquireSRWLockShared(BipSessionLock);
    v30 = Sid2;
    *v29 |= v28;
    SessionIdBySid = BipUserInfoGetSessionIdBySid(v30);
    if ( SessionIdBySid == -1 )
    {
      v36 = ~(1 << dword_1800C46D8);
      RtlReleaseSRWLockShared(BipSessionLock);
      *v29 &= v36;
    }
    else
    {
      ActivationContext = BipSessionGetActivationContext(SessionIdBySid);
      v32 = ~(1 << dword_1800C46D8);
      RtlReleaseSRWLockShared(BipSessionLock);
      *v29 &= v32;
      if ( ActivationContext )
      {
        v14 = *(WCHAR **)packageFamilyNameLength;
        v16 = ActivationContext;
LABEL_34:
        v33 = (_DWORD *)v59;
        v17 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, BSTR, __int64, OLECHAR *, PCWSTR *, int, __int64))(*(_QWORD *)ActivationContext + 32LL))(
                ActivationContext,
                v20,
                bstrString,
                v54,
                v59,
                v27,
                &v53,
                1,
                v58);
        if ( v17 >= 0 )
        {
          if ( *v33 == 1 || (unsigned int)(*v33 - 2) < 2 )
          {
            v35 = v53;
            if ( !v53 )
              goto LABEL_44;
            packageFamilyNameLength[0] = 65;
            *(_OWORD *)v14 = 0;
            *((_OWORD *)v14 + 1) = 0;
            packageRelativeApplicationIdLength = 65;
            *((_OWORD *)v14 + 2) = 0;
            *((_OWORD *)v14 + 3) = 0;
            *((_OWORD *)v14 + 4) = 0;
            *((_OWORD *)v14 + 5) = 0;
            *((_OWORD *)v14 + 6) = 0;
            *((_OWORD *)v14 + 7) = 0;
            v14[64] = 0;
            if ( ParseApplicationUserModelId(
                   v35,
                   packageFamilyNameLength,
                   (PWSTR)&packageFamilyName,
                   &packageRelativeApplicationIdLength,
                   v14) )
            {
              v18 = 10000;
              v19 = -1073741823;
            }
            else
            {
LABEL_44:
              v18 = 0;
              v19 = 0;
              v17 = 0;
            }
          }
          else
          {
            v18 = 9000;
            v19 = -1073741811;
            v17 = -2147024809;
          }
        }
        else
        {
          v34 = -1073741811;
          v18 = 8000;
          if ( v17 != -2147221164 )
            v34 = -1073741823;
          v19 = v34;
        }
        goto LABEL_47;
      }
    }
    v18 = 7000;
    v19 = -1073741729;
LABEL_47:
    SysFreeString(v20);
    LOBYTE(v20) = v47;
    SysFreeString(bstrString);
    SysFreeString(v54);
    if ( v27 )
      SysFreeString(v27);
    goto LABEL_49;
  }
  v18 = 2000;
  v19 = -1073741801;
  LOBYTE(v20) = 0;
LABEL_49:
  v12 = strIn;
LABEL_50:
  if ( v53 )
    SysFreeString((BSTR)v53);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( (_BYTE)v20 )
    CoUninitialize();
  if ( v19 < 0 )
  {
    if ( v17 >= 0 )
    {
      v37 = RtlNtStatusToDosErrorNoTeb(v19);
      v17 = v37;
      if ( v37 > 0 )
        v17 = (unsigned __int16)v37 | 0x80070000;
    }
    if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      v38 = &BipTraceLoggingNullSid;
      packageFamilyNameLength[0] = v18;
      packageRelativeApplicationIdLength = v17;
      if ( Sid2 )
        v38 = (__int64 *)Sid2;
      LODWORD(bstrString) = v19;
      v78 = 4;
      v77 = packageFamilyNameLength;
      v76 = 4;
      p_packageRelativeApplicationIdLength = &packageRelativeApplicationIdLength;
      p_bstrString = &bstrString;
      v39 = -1;
      v74 = 4;
      if ( v12 )
      {
        v40 = -1;
        do
          v41 = v12[++v40] == 0;
        while ( !v41 );
        v42 = 2 * v40 + 2;
      }
      else
      {
        v12 = (OLECHAR *)&qword_1800A1670;
        v42 = 2;
      }
      v71 = v42;
      v43 = *(__int64 **)&EventDescriptor.Id;
      v70 = v12;
      v72 = 0;
      if ( *(_QWORD *)&EventDescriptor.Id )
      {
        do
          v41 = *(_WORD *)(*(_QWORD *)&EventDescriptor.Id + 2 * v39++ + 2) == 0;
        while ( !v41 );
        v44 = 2 * v39 + 2;
      }
      else
      {
        v43 = &qword_1800A1670;
        v44 = 2;
      }
      v68 = v44;
      v67 = v43;
      v69 = 0;
      v45 = *((unsigned __int8 *)v38 + 1);
      v64 = v38;
      v66 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 3;
      v65 = 4 * v45 + 8;
      *(_DWORD *)&EventDescriptor.Level = 2;
      wcscpy((wchar_t *)&packageFamilyName, (const wchar_t *)&off_1800C30A0);
      packageFamilyName.Size = *(unsigned __int16 *)off_1800C30A0;
      v61 = &unk_1800AE538;
      packageFamilyName.Reserved = 2;
      v62 = 91;
      v63 = 1;
      LODWORD(strIn) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &packageFamilyName);
    }
  }
  *v56 = v17;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180053db0  push    rbp
0x180053db2  push    rbx
0x180053db3  push    rsi
0x180053db4  push    rdi
0x180053db5  push    r12
0x180053db7  push    r13
0x180053db9  push    r14
0x180053dbb  push    r15
0x180053dbd  lea     rbp, [rsp-178h]
0x180053dc5  sub     rsp, 278h
0x180053dcc  mov     rax, cs:__security_cookie
0x180053dd3  xor     rax, rsp
0x180053dd6  mov     [rbp+1B0h+var_50], rax
0x180053ddd  mov     rax, [rbp+1B0h+arg_20]
0x180053de4  mov     r12, r8
0x180053de7  mov     rbx, [rbp+1B0h+arg_30]
0x180053dee  mov     r15, rdx
0x180053df1  mov     rdi, [rbp+1B0h+packageRelativeApplicationId]
0x180053df8  xor     edx, edx; Val
0x180053dfa  mov     [rsp+2B0h+bstrString], rax
0x180053dff  mov     r14d, r9d
0x180053e02  mov     eax, [rbp+1B0h+arg_28]
0x180053e08  mov     [rsp+2B0h+packageRelativeApplicationIdLength], eax
0x180053e0c  mov     rax, [rbp+1B0h+arg_40]
0x180053e13  mov     [rbp+1B0h+var_200], rax
0x180053e17  mov     rax, [rbp+1B0h+arg_50]
0x180053e1e  mov     [rbp+1B0h+var_208], rax
0x180053e22  mov     rax, [rbp+1B0h+arg_58]
0x180053e29  mov     [rbp+1B0h+var_220], rax
0x180053e2d  xor     al, al
0x180053e2f  mov     [rsp+2B0h+var_260], al
0x180053e33  xor     eax, eax
0x180053e35  mov     [rsp+2B0h+strIn], r8
0x180053e3a  mov     r13d, eax
0x180053e3d  mov     [rbp+1B0h+Sid2], rcx
0x180053e41  mov     r8d, 104h; Size
0x180053e47  lea     rcx, [rbp+1B0h+applicationUserModelId]; void *
0x180053e4b  mov     [rsp+2B0h+var_238], rax
0x180053e50  mov     esi, eax
0x180053e52  mov     [rsp+2B0h+applicationUserModelIdLength], eax
0x180053e56  mov     qword ptr [rbp+1B0h+EventDescriptor.Id], rbx
0x180053e5a  mov     qword ptr [rsp+2B0h+packageFamilyNameLength], rdi
0x180053e5f  call    memset_0
0x180053e64  movzx   eax, cs:g_BiActInitialized
0x180053e6b  test    al, al
0x180053e6d  jnz     short loc_180053E81
0x180053e6f  mov     edi, 3E8h
0x180053e74  mov     ebx, 0C000005Fh
0x180053e79  xor     r14b, r14b
0x180053e7c  jmp     loc_180054202
0x180053e81  add     rbx, 100h
0x180053e88  jz      short loc_180053EBC
0x180053e8a  mov     ecx, 41h ; 'A'
0x180053e8f  mov     rax, rbx
0x180053e92  cmp     [rax], si
0x180053e95  jz      short loc_180053EA1
0x180053e97  add     rax, 2
0x180053e9b  sub     rcx, 1
0x180053e9f  jnz     short loc_180053E92
0x180053ea1  test    rcx, rcx
0x180053ea4  jz      short loc_180053EBC
0x180053ea6  xor     eax, eax
0x180053ea8  mov     edx, 41h ; 'A'
0x180053ead  sub     rdx, rcx
0x180053eb0  add     rdx, rdx
0x180053eb3  test    rcx, rcx
0x180053eb6  cmovz   rdx, rax
0x180053eba  jmp     short loc_180053EBE
0x180053ebc  xor     edx, edx
0x180053ebe  shr     edx, 1; ui
0x180053ec0  mov     rcx, rbx; strIn
0x180053ec3  call    cs:__imp_SysAllocStringLen
0x180053ec9  mov     [rbp+1B0h+var_230], rax
0x180053ecd  mov     r12, rax
0x180053ed0  test    rax, rax
0x180053ed3  jnz     short loc_180053EE7
0x180053ed5  mov     edi, 7D0h
0x180053eda  mov     ebx, 0C0000017h
0x180053edf  xor     r14b, r14b
0x180053ee2  jmp     loc_1800541FD
0x180053ee7  mov     rcx, [rsp+2B0h+strIn]; strIn
0x180053eec  shr     r14d, 1
0x180053eef  mov     edx, r14d; ui
0x180053ef2  call    cs:__imp_SysAllocStringLen
0x180053ef8  mov     r14, rax
0x180053efb  test    rax, rax
0x180053efe  jnz     short loc_180053F18
0x180053f00  mov     rcx, r12; bstrString
0x180053f03  mov     edi, 0BB8h
0x180053f08  mov     ebx, 0C0000017h
0x180053f0d  call    cs:__imp_SysFreeString
0x180053f13  jmp     loc_1800541FD
0x180053f18  mov     rcx, [rsp+2B0h+bstrString]
0x180053f1d  test    rcx, rcx
0x180053f20  jz      short loc_180053F2A
0x180053f22  mov     edx, [rsp+2B0h+packageRelativeApplicationIdLength]
0x180053f26  shr     edx, 1
0x180053f28  jmp     short loc_180053F36
0x180053f2a  mov     edx, 17h; ui
0x180053f2f  lea     rcx, strIn; "Windows.BackgroundTasks"
0x180053f36  call    cs:__imp_SysAllocStringLen
0x180053f3c  mov     [rsp+2B0h+bstrString], rax
0x180053f41  test    rax, rax
0x180053f44  jnz     short loc_180053F6A
0x180053f46  mov     rcx, r14; bstrString
0x180053f49  mov     edi, 0FA0h
0x180053f4e  mov     ebx, 0C0000017h
0x180053f53  call    cs:__imp_SysFreeString
0x180053f59  mov     rcx, r12; bstrString
0x180053f5c  call    cs:__imp_SysFreeString
0x180053f62  xor     r14b, r14b
0x180053f65  jmp     loc_1800541FD
0x180053f6a  xor     r12d, r12d
0x180053f6d  cmp     [rdi], si
0x180053f70  jz      short loc_180053FC3
0x180053f72  lea     r9, [rbp+1B0h+applicationUserModelId]; applicationUserModelId
0x180053f76  mov     [rsp+2B0h+applicationUserModelIdLength], 82h
0x180053f7e  lea     r8, [rsp+2B0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180053f83  mov     rdx, rdi; packageRelativeApplicationId
0x180053f86  mov     rcx, rbx; packageFamilyName
0x180053f89  call    cs:__imp_FormatApplicationUserModelId
0x180053f8f  test    eax, eax
0x180053f91  jz      short loc_180053FA2
0x180053f93  mov     edi, 1388h
0x180053f98  mov     ebx, 0C0000001h
0x180053f9d  jmp     loc_1800541CB
0x180053fa2  lea     rcx, [rbp+1B0h+applicationUserModelId]; psz
0x180053fa6  call    cs:__imp_SysAllocString
0x180053fac  mov     r12, rax
0x180053faf  test    rax, rax
0x180053fb2  jnz     short loc_180053FC3
0x180053fb4  mov     edi, 157Ch
0x180053fb9  mov     ebx, 0C0000017h
0x180053fbe  jmp     loc_1800541CB
0x180053fc3  xor     edx, edx; dwCoInit
0x180053fc5  xor     ecx, ecx; pvReserved
0x180053fc7  call    cs:__imp_CoInitializeEx
0x180053fcd  mov     esi, eax
0x180053fcf  test    eax, eax
0x180053fd1  jns     short loc_180053FE2
0x180053fd3  mov     edi, 1770h
0x180053fd8  mov     ebx, 0C0000001h
0x180053fdd  jmp     loc_1800541CB
0x180053fe2  mov     [rsp+2B0h+var_260], 1
0x180053fe7  test    r15, r15
0x180053fea  jz      short loc_180054003
0x180053fec  mov     rax, [r15]
0x180053fef  mov     rcx, r15
0x180053ff2  mov     r13, r15
0x180053ff5  mov     rax, [rax+8]
0x180053ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ffe  jmp     loc_18005409F
0x180054003  mov     ecx, cs:dword_1800C46D8
0x180054009  mov     ebx, 1
0x18005400e  mov     rax, gs:58h
0x180054017  shl     ebx, cl
0x180054019  mov     ecx, cs:_tls_index
0x18005401f  mov     edx, 4
0x180054024  mov     rdi, [rax+rcx*8]
0x180054028  add     rdi, rdx
0x18005402b  cmp     [rdi], ebx
0x18005402d  jb      short loc_180054045
0x18005402f  call    cs:__imp_IsDebuggerPresent
0x180054035  test    eax, eax
0x180054037  jz      short loc_180054045
0x180054039  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x180054040  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180054045  lea     rcx, BipSessionLock
0x18005404c  call    cs:__imp_RtlAcquireSRWLockShared
0x180054052  mov     rcx, [rbp+1B0h+Sid2]; Sid2
0x180054056  or      [rdi], ebx
0x180054058  call    BipUserInfoGetSessionIdBySid
0x18005405d  cmp     eax, 0FFFFFFFFh
0x180054060  jz      loc_1800541A3
0x180054066  mov     ecx, eax
0x180054068  call    BipSessionGetActivationContext
0x18005406d  mov     ecx, cs:dword_1800C46D8
0x180054073  mov     ebx, 1
0x180054078  shl     ebx, cl
0x18005407a  mov     r15, rax
0x18005407d  lea     rcx, BipSessionLock
0x180054084  not     ebx
0x180054086  call    cs:__imp_RtlReleaseSRWLockShared
0x18005408c  and     [rdi], ebx
0x18005408e  test    r15, r15
0x180054091  jz      loc_1800541C1
0x180054097  mov     rdi, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x18005409c  mov     r13, r15
0x18005409f  mov     rcx, [rbp+1B0h+var_208]
0x1800540a3  mov     rdx, r14
0x1800540a6  mov     rax, [r15]
0x1800540a9  mov     rbx, [rbp+1B0h+var_200]
0x1800540ad  mov     r9, [rbp+1B0h+var_230]
0x1800540b1  mov     r8, [rsp+2B0h+bstrString]
0x1800540b6  mov     rax, [rax+20h]
0x1800540ba  mov     [rsp+2B0h+var_270], rcx
0x1800540bf  lea     rcx, [rsp+2B0h+var_238]
0x1800540c4  mov     [rsp+2B0h+var_278], 1
0x1800540cc  mov     [rsp+2B0h+var_280], rcx
0x1800540d1  mov     rcx, r15
0x1800540d4  mov     [rsp+2B0h+UserData], r12
0x1800540d9  mov     [rsp+2B0h+var_290], rbx
0x1800540de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540e3  mov     esi, eax
0x1800540e5  test    eax, eax
0x1800540e7  jns     short loc_180054108
0x1800540e9  mov     ebx, 0C0000001h
0x1800540ee  cmp     esi, 80040154h
0x1800540f4  mov     eax, 0C000000Dh
0x1800540f9  mov     edi, 1F40h
0x1800540fe  cmovnz  eax, ebx
0x180054101  mov     ebx, eax
0x180054103  jmp     loc_1800541CB
0x180054108  mov     ecx, [rbx]
0x18005410a  sub     ecx, 1
0x18005410d  jz      short loc_18005412D
0x18005410f  sub     ecx, 1
0x180054112  jz      short loc_18005412D
0x180054114  cmp     ecx, 1
0x180054117  jz      short loc_18005412D
0x180054119  mov     edi, 2328h
0x18005411e  mov     ebx, 0C000000Dh
0x180054123  mov     esi, 80070057h
0x180054128  jmp     loc_1800541CB
0x18005412d  mov     rcx, [rsp+2B0h+var_238]; applicationUserModelId
0x180054132  test    rcx, rcx
0x180054135  jz      short loc_18005419B
0x180054137  xorps   xmm0, xmm0
0x18005413a  mov     [rsp+2B0h+packageFamilyNameLength], 41h ; 'A'
0x180054142  movups  xmmword ptr [rdi], xmm0
0x180054145  xor     eax, eax
0x180054147  lea     r9, [rsp+2B0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18005414c  movups  xmmword ptr [rdi+10h], xmm0
0x180054150  lea     r8, [rbp+1B0h+packageFamilyName]; packageFamilyName
0x180054154  mov     [rsp+2B0h+packageRelativeApplicationIdLength], 41h ; 'A'
0x18005415c  movups  xmmword ptr [rdi+20h], xmm0
0x180054160  lea     rdx, [rsp+2B0h+packageFamilyNameLength]; packageFamilyNameLength
0x180054165  mov     [rsp+2B0h+var_290], rdi; packageRelativeApplicationId
0x18005416a  movups  xmmword ptr [rdi+30h], xmm0
0x18005416e  movups  xmmword ptr [rdi+40h], xmm0
0x180054172  movups  xmmword ptr [rdi+50h], xmm0
0x180054176  movups  xmmword ptr [rdi+60h], xmm0
0x18005417a  movups  xmmword ptr [rdi+70h], xmm0
0x18005417e  mov     [rdi+80h], ax
0x180054185  call    cs:__imp_ParseApplicationUserModelId
0x18005418b  test    eax, eax
0x18005418d  jz      short loc_18005419B
0x18005418f  mov     edi, 2710h
0x180054194  mov     ebx, 0C0000001h
0x180054199  jmp     short loc_1800541CB
0x18005419b  xor     edi, edi
0x18005419d  xor     ebx, ebx
0x18005419f  xor     esi, esi
0x1800541a1  jmp     short loc_1800541CB
0x1800541a3  mov     ecx, cs:dword_1800C46D8
0x1800541a9  mov     ebx, 1
0x1800541ae  shl     ebx, cl
0x1800541b0  lea     rcx, BipSessionLock
0x1800541b7  not     ebx
0x1800541b9  call    cs:__imp_RtlReleaseSRWLockShared
0x1800541bf  and     [rdi], ebx
0x1800541c1  mov     edi, 1B58h
0x1800541c6  mov     ebx, 0C000005Fh
0x1800541cb  mov     rcx, r14; bstrString
0x1800541ce  call    cs:__imp_SysFreeString
0x1800541d4  mov     rcx, [rsp+2B0h+bstrString]; bstrString
0x1800541d9  movzx   r14d, [rsp+2B0h+var_260]
0x1800541df  call    cs:__imp_SysFreeString
0x1800541e5  mov     rcx, [rbp+1B0h+var_230]; bstrString
0x1800541e9  call    cs:__imp_SysFreeString
0x1800541ef  test    r12, r12
0x1800541f2  jz      short loc_1800541FD
0x1800541f4  mov     rcx, r12; bstrString
0x1800541f7  call    cs:__imp_SysFreeString
0x1800541fd  mov     r12, [rsp+2B0h+strIn]
0x180054202  mov     rcx, [rsp+2B0h+var_238]; bstrString
0x180054207  test    rcx, rcx
0x18005420a  jz      short loc_180054212
0x18005420c  call    cs:__imp_SysFreeString
0x180054212  test    r13, r13
0x180054215  jz      short loc_180054227
0x180054217  mov     rax, [r13+0]
0x18005421b  mov     rcx, r13
0x18005421e  mov     rax, [rax+10h]
0x180054222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054227  test    r14b, r14b
0x18005422a  jz      short loc_180054232
0x18005422c  call    cs:__imp_CoUninitialize
0x180054232  test    ebx, ebx
0x180054234  jns     loc_1800543F9
0x18005423a  test    esi, esi
0x18005423c  js      short loc_180054255
0x18005423e  mov     ecx, ebx; Status
0x180054240  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180054246  mov     esi, eax
0x180054248  test    eax, eax
0x18005424a  jle     short loc_180054255
0x18005424c  movzx   esi, ax
0x18005424f  or      esi, 80070000h
0x180054255  mov     eax, cs:dword_1800C3098
  ... truncated ...
```
