# UpdateNlsInfoCache

- ea: `0x180071550`
- end: `0x180071b80`
- name: `UpdateNlsInfoCache`
- size: `1584`
- prototype: ``
- caller_count: `8`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000dd50`
- `0x1800108d0`
- `0x1800181e0`
- `0x180019090`
- `0x18001a230`
- `0x18001b3a0`
- `0x18001d7c0`
- `0x180037730`

## callees

- `0x180010080`
- `0x180011b90`
- `0x180012f10`
- `0x18001a1b8`
- `0x18001c970`
- `0x18001e794`
- `0x18001e8c0`
- `0x18001ea10`
- `0x180037714`
- `0x180071550`
- `0x18007217c`
- `0x180072474`
- `0x180122e60`
- `0x18012d119`
- `0x180138ebc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180071aa7`
- `ntdll!RtlInitUnicodeString` at `0x180071aa7`
- `ntdll!NtOpenKey` at `0x180071aed`
- `ntdll!NtOpenKey` at `0x180071aed`
- `ntdll!NtCreateKey` at `0x180071b1f`
- `ntdll!NtCreateKey` at `0x180071b1f`
- `ntdll!RtlOpenCurrentUser` at `0x18007190a`
- `ntdll!RtlOpenCurrentUser` at `0x18007190a`
- `ntdll!CsrClientCallServer` at `0x18007186a`
- `ntdll!CsrClientCallServer` at `0x18007186a`
- `ntdll!CsrCaptureMessageBuffer` at `0x18007184a`
- `ntdll!CsrCaptureMessageBuffer` at `0x18007184a`
- `ntdll!CsrFreeCaptureBuffer` at `0x18007188c`
- `ntdll!CsrFreeCaptureBuffer` at `0x18007188c`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800715f9`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800715f9`
- `ntdll!NtClose` at `0x18007167d`
- `ntdll!NtClose` at `0x1800719a3`
- `ntdll!NtClose` at `0x180071b31`
- `ntdll!NtClose` at `0x180071b69`
- `ntdll!NtClose` at `0x18007167d`
- `ntdll!NtClose` at `0x1800719a3`
- `ntdll!NtClose` at `0x180071b31`
- `ntdll!NtClose` at `0x180071b69`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007158c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800716eb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007158c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800716eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800717d1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007181a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800717d1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007181a`

## pseudocode

```c
signed __int16 __fastcall UpdateNlsInfoCache(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r14d
  bool v5; // zf
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v7; // rsi
  NTSTATUS v8; // edi
  HANDLE v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rax
  DWORD v12; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v15; // r8
  DWORD v16; // edi
  const WCHAR *v17; // rcx
  __int64 NamedLocaleHashNode; // rax
  signed __int16 result; // ax
  int GlobalizationUserModelType; // eax
  int v21; // eax
  __int64 v22; // rcx
  WCHAR *v23; // rax
  __int64 v24; // r8
  const WCHAR *v25; // rdx
  WCHAR *v26; // r9
  __int64 v27; // rcx
  WCHAR *v28; // rcx
  __int64 v29; // rdx
  int v30; // eax
  NTSTATUS v31; // edi
  HANDLE v32; // rcx
  void *v33; // rdi
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  ULONG Disposition; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+54h] [rbp-ACh] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ApiMessage[32]; // [rsp+A0h] [rbp-60h] BYREF
  PVOID CapturedData; // [rsp+E0h] [rbp-20h] BYREF
  int v42; // [rsp+E8h] [rbp-18h]

  v3 = a2;
  if ( *(_WORD *)(a1 + 1684) != 3 )
    RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
  if ( *(_WORD *)(a1 + 1684) == 3 || *(_WORD *)(a1 + 1686) )
  {
    v5 = *(_WORD *)(a1 + 1684) == 1;
    *(_WORD *)(a1 + 1686) = 2;
    if ( v5 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v7 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v42 = 1660;
        v8 = CsrClientCallServer(ApiMessage, v7, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v8 >= 0 )
          memcpy_0((void *)(a1 + 24), CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v7);
      }
      else
      {
        v8 = -1073741801;
      }
      if ( *(_WORD *)(a1 + 1684) == 1 && v8 >= 0 )
      {
LABEL_14:
        if ( *(_WORD *)(a1 + 24) == 0xFFFF )
        {
          *(_QWORD *)(a1 + 16) = 0;
        }
        else
        {
          v10 = gpOneCustomHashNode;
          _InterlockedExchange64((volatile __int64 *)(a1 + 16), GetNamedLocaleHashNode(a1 + 26, 0));
          if ( !v10 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
        }
        if ( *(_QWORD *)(a1 + 16) )
        {
LABEL_37:
          result = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 1686), 0, 2);
          if ( *(_WORD *)(a1 + 1684) == 3 )
            return result;
          return RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
        }
        v11 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_36:
          *(_QWORD *)(a1 + 16) = v11;
          goto LABEL_37;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_35;
        v12 = gSystemLocale;
        for ( i = *((_QWORD *)P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); i; i = *(_QWORD *)(i + 88) )
        {
          if ( *(_DWORD *)i == gSystemLocale )
            break;
        }
        gpSysLocHashN = i;
        if ( i )
          goto LABEL_35;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_69;
        WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( WindowsLocaleData )
        {
          if ( (_WORD)v12 != 127 )
          {
            v16 = HIWORD(v12);
            if ( (v16 & 0xF) == 0 )
            {
              v17 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_31:
              NamedLocaleHashNode = MakeNamedLocaleHashNode(v17, 0);
              goto LABEL_32;
            }
            v29 = WindowsLocaleData[54];
            v17 = (const WCHAR *)qword_18039EC90;
            if ( (_DWORD)v29 )
              v17 = (const WCHAR *)(qword_18039EC90
                                  + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v29 + 2LL * (v16 & 0xF)) - 2)
                                  + 2);
            if ( v17 && *v17 )
              goto LABEL_31;
LABEL_69:
            gpSysLocHashN = 0;
LABEL_33:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_35;
          }
          NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v12, v15, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_69;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            NamedLocaleHashNode = FindLocaleHashNode(v12);
          }
          else
          {
            NamedLocaleHashNode = 0;
          }
        }
LABEL_32:
        gpSysLocHashN = NamedLocaleHashNode;
        if ( !NamedLocaleHashNode )
          goto LABEL_33;
LABEL_35:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v11 = gpSysLocHashN;
        goto LABEL_36;
      }
    }
    Handle = 0;
    if ( (HANDLE *)a1 != &gNlsProcessLocalCache )
    {
      OpenRegistryInternationalKey(&Handle, 0x20019u);
      goto LABEL_11;
    }
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_11:
      v9 = Handle;
      NlsUpdateCacheInfo(a1 + 24, Handle, v3);
      if ( *(_WORD *)(a1 + 1684) == 3 && v9 )
        NtClose(v9);
      goto LABEL_14;
    }
    KeyHandle = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, a2, a3);
    if ( GlobalizationUserModelType == 1 )
    {
      v21 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v30 = GlobalizationUserModelType - 2;
      if ( v30 )
      {
        if ( v30 != 1 )
        {
LABEL_64:
          SetLastError_0(0x3F1u);
          goto LABEL_11;
        }
        v37 = 0;
        v21 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, &v37);
      }
      else
      {
        v21 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v21 >= 0 )
    {
      ApiMessage[0] = 0;
      v22 = 512;
      v23 = ApiMessage;
      do
      {
        if ( !*v23 )
          break;
        ++v23;
        --v22;
      }
      while ( v22 );
      if ( !v22 )
        goto LABEL_62;
      v24 = v22;
      v25 = L"Control Panel\\International";
      v26 = &ApiMessage[512 - v22];
      v27 = 2147483646;
      do
      {
        if ( !v27 )
          break;
        if ( !*v25 )
          break;
        *v26++ = *v25++;
        --v27;
        --v24;
      }
      while ( v24 );
      v28 = v26 - 1;
      if ( v24 )
        v28 = v26;
      *v28 = 0;
      if ( v24 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v31 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v31 < 0 )
          v31 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v31 >= 0 )
        {
          v32 = Handle;
        }
        else
        {
          v32 = 0;
          Handle = 0;
        }
        if ( v31 >= 0 )
        {
          v33 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v32,
                          0);
          if ( v33 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v33;
          }
          goto LABEL_11;
        }
      }
      else
      {
LABEL_62:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
    goto LABEL_64;
  }
  return RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
}

```

## disassembly

```asm
0x180071550  push    rbp
0x180071552  push    rbx
0x180071553  push    r14
0x180071555  lea     rbp, [rsp-3C0h]
0x18007155d  sub     rsp, 4C0h
0x180071564  mov     rax, cs:__security_cookie
0x18007156b  xor     rax, rsp
0x18007156e  mov     [rbp+3D0h+var_30], rax
0x180071575  cmp     word ptr [rcx+694h], 3
0x18007157d  mov     r14d, edx
0x180071580  mov     rbx, rcx
0x180071583  jz      short loc_180071592
0x180071585  lea     rcx, gNlsProcessCacheLock
0x18007158c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180071592  cmp     word ptr [rbx+694h], 3
0x18007159a  jnz     loc_1800718A4
0x1800715a0  mov     [rsp+4D0h+arg_10], rdi
0x1800715a8  mov     [rsp+4D0h+var_18], r12
0x1800715b0  mov     r12d, 2
0x1800715b6  mov     [rsp+4D0h+var_20], r15
0x1800715be  xor     r15d, r15d
0x1800715c1  cmp     word ptr [rbx+694h], 1
0x1800715c9  mov     edi, r15d
0x1800715cc  mov     [rbx+696h], r12w
0x1800715d4  jnz     short loc_180071626
0x1800715d6  xor     edx, edx; Val
0x1800715d8  mov     [rsp+4D0h+arg_8], rsi
0x1800715e0  mov     r8d, 3B8h; Size
0x1800715e6  lea     rcx, [rbp+3D0h+ApiMessage]; void *
0x1800715ea  call    memset_0
0x1800715ef  mov     edx, 67Ch; BufferSize
0x1800715f4  mov     ecx, 1; ArgumentCount
0x1800715f9  call    cs:__imp_CsrAllocateCaptureBuffer
0x1800715ff  mov     rsi, rax
0x180071602  test    rax, rax
0x180071605  jnz     loc_18007183B
0x18007160b  mov     edi, 0C0000017h
0x180071610  cmp     word ptr [rbx+694h], 1
0x180071618  mov     rsi, [rsp+4D0h+arg_8]
0x180071620  jz      loc_180071897
0x180071626  lea     rax, gNlsProcessLocalCache
0x18007162d  mov     [rsp+4D0h+Handle], r15
0x180071632  cmp     rbx, rax
0x180071635  jnz     loc_180071A8B
0x18007163b  mov     rax, cs:gNlsProcessLocalCache
0x180071642  test    rax, rax
0x180071645  jz      loc_1800718C2
0x18007164b  mov     rax, cs:gNlsProcessLocalCache
0x180071652  mov     [rsp+4D0h+Handle], rax
0x180071657  mov     rdi, [rsp+4D0h+Handle]
0x18007165c  lea     rcx, [rbx+18h]
0x180071660  mov     rdx, rdi
0x180071663  mov     r8d, r14d
0x180071666  call    NlsUpdateCacheInfo
0x18007166b  cmp     word ptr [rbx+694h], 3
0x180071673  jnz     short loc_180071683
0x180071675  test    rdi, rdi
0x180071678  jz      short loc_180071683
0x18007167a  mov     rcx, rdi; Handle
0x18007167d  call    cs:__imp_NtClose
0x180071683  mov     eax, 0FFFFh
0x180071688  cmp     [rbx+18h], ax
0x18007168c  jz      loc_1800718B9
0x180071692  mov     rdi, cs:gpOneCustomHashNode
0x180071699  lea     rcx, [rbx+1Ah]
0x18007169d  xor     edx, edx
0x18007169f  call    GetNamedLocaleHashNode
0x1800716a4  xchg    rax, [rbx+10h]
0x1800716a8  test    rdi, rdi
0x1800716ab  jnz     short loc_1800716BD
0x1800716ad  cmp     cs:gpOneCustomHashNode, r15
0x1800716b4  jz      short loc_1800716BD
0x1800716b6  mov     cs:gpOneCustomHashNode, r15
0x1800716bd  cmp     [rbx+10h], r15
0x1800716c1  jnz     loc_1800717E2
0x1800716c7  mov     rax, cs:gpSysLocHashN
0x1800716ce  test    rax, rax
0x1800716d1  jnz     loc_1800717DE
0x1800716d7  cmp     cs:BasepIsSecureProcess, r15b
0x1800716de  jnz     loc_1800717DE
0x1800716e4  lea     rcx, gTblPtrsLock
0x1800716eb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800716f1  cmp     cs:gpSysLocHashN, r15
0x1800716f8  jnz     loc_1800717CA
0x1800716fe  mov     edi, cs:gSystemLocale
0x180071704  mov     rax, cs:P
0x18007170b  mov     ecx, edi
0x18007170d  shr     rcx, 7
0x180071711  xor     rcx, rdi
0x180071714  shr     rcx, 7
0x180071718  xor     rcx, rdi
0x18007171b  and     ecx, 7Fh
0x18007171e  mov     rdx, [rax+rcx*8]
0x180071722  test    rdx, rdx
0x180071725  jz      short loc_18007172F
0x180071727  cmp     [rdx], edi
0x180071729  jnz     loc_1800719F6
0x18007172f  mov     cs:gpSysLocHashN, rdx
0x180071736  test    rdx, rdx
0x180071739  jnz     loc_1800717CA
0x18007173f  test    edi, 0FFF00000h
0x180071745  jnz     loc_1800719EA
0x18007174b  cmp     cs:BasepIsSecureProcess, r15b
0x180071752  jnz     loc_1800719EA
0x180071758  mov     ecx, edi
0x18007175a  call    GetWindowsLocaleData
0x18007175f  test    rax, rax
0x180071762  jz      loc_180071A08
0x180071768  cmp     di, 7Fh
0x18007176c  jz      loc_180071A2B
0x180071772  shr     edi, 10h
0x180071775  test    dil, 0Fh
0x180071779  jnz     loc_1800719B8
0x18007177f  mov     ecx, [rax]
0x180071781  mov     rax, cs:qword_18039EC90
0x180071788  add     rax, r12
0x18007178b  lea     rcx, [rax+rcx*2]
0x18007178f  xor     edx, edx
0x180071791  call    MakeNamedLocaleHashNode
0x180071796  mov     cs:gpSysLocHashN, rax
0x18007179d  test    rax, rax
0x1800717a0  jnz     short loc_1800717CA
0x1800717a2  xor     edx, edx
0x1800717a4  lea     rcx, aEnUs; "en-US"
0x1800717ab  call    MakeNamedLocaleHashNode
0x1800717b0  mov     cs:gpSysLocHashN, rax
0x1800717b7  test    rax, rax
0x1800717ba  jnz     short loc_1800717CA
0x1800717bc  mov     rdx, cs:gpInvLocHashN
0x1800717c3  mov     cs:gpSysLocHashN, rdx
0x1800717ca  lea     rcx, gTblPtrsLock
0x1800717d1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800717d7  mov     rax, cs:gpSysLocHashN
0x1800717de  mov     [rbx+10h], rax
0x1800717e2  mov     eax, r12d
0x1800717e5  mov     edx, r15d
0x1800717e8  lock cmpxchg [rbx+696h], dx
0x1800717f1  cmp     word ptr [rbx+694h], 3
0x1800717f9  mov     r15, [rsp+4D0h+var_20]
0x180071801  mov     r12, [rsp+4D0h+var_18]
0x180071809  mov     rdi, [rsp+4D0h+arg_10]
0x180071811  jz      short loc_180071820
0x180071813  lea     rcx, gNlsProcessCacheLock
0x18007181a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180071820  mov     rcx, [rbp+3D0h+var_30]
0x180071827  xor     rcx, rsp; StackCookie
0x18007182a  call    __security_check_cookie
0x18007182f  add     rsp, 4C0h
0x180071836  pop     r14
0x180071838  pop     rbx
0x180071839  pop     rbp
0x18007183a  retn
0x18007183b  lea     r9, [rbp+3D0h+CapturedData]; CapturedData
0x18007183f  xor     edx, edx; MessageBuffer
0x180071841  mov     r8d, 67Ch; MessageLength
0x180071847  mov     rcx, rsi; CaptureBuffer
0x18007184a  call    cs:__imp_CsrCaptureMessageBuffer
0x180071850  mov     r9d, 10h; DataLength
0x180071856  mov     [rbp+3D0h+var_3E8], 67Ch
0x18007185d  mov     r8d, 1001Bh; ApiNumber
0x180071863  lea     rcx, [rbp+3D0h+ApiMessage]; ApiMessage
0x180071867  mov     rdx, rsi; CaptureBuffer
0x18007186a  call    cs:__imp_CsrClientCallServer
0x180071870  mov     edi, eax
0x180071872  test    eax, eax
0x180071874  js      short loc_180071889
0x180071876  mov     rdx, [rbp+3D0h+CapturedData]; Src
0x18007187a  lea     rcx, [rbx+18h]; void *
0x18007187e  mov     r8d, 67Ch; Size
0x180071884  call    memcpy_0
0x180071889  mov     rcx, rsi; CaptureBuffer
0x18007188c  call    cs:__imp_CsrFreeCaptureBuffer
0x180071892  jmp     loc_180071610
0x180071897  test    edi, edi
0x180071899  jns     loc_180071683
0x18007189f  jmp     loc_180071626
0x1800718a4  movzx   eax, word ptr [rbx+696h]
0x1800718ab  test    ax, ax
0x1800718ae  jnz     loc_1800715A0
0x1800718b4  jmp     loc_180071813
0x1800718b9  mov     [rbx+10h], r15
0x1800718bd  jmp     loc_1800716BD
0x1800718c2  mov     rcx, [rsp+4D0h+Handle]
0x1800718c7  test    rcx, rcx
0x1800718ca  jnz     loc_180071B4B
0x1800718d0  xorps   xmm0, xmm0
0x1800718d3  mov     [rsp+4D0h+KeyHandle], r15
0x1800718d8  movups  xmmword ptr [rsp+4D0h+ObjectAttributes.ObjectName], xmm0
0x1800718dd  xor     eax, eax
0x1800718df  mov     [rsp+4D0h+var_480], r15d
0x1800718e4  movups  xmmword ptr [rsp+4D0h+ObjectAttributes+1Ch], xmm0
0x1800718e9  movups  xmmword ptr [rsp+4D0h+ObjectAttributes.Length], xmm0
0x1800718ee  movups  xmmword ptr [rbp+3D0h+DestinationString.Length], xmm0
0x1800718f2  call    GetGlobalizationUserModelType
0x1800718f7  cmp     eax, 1
0x1800718fa  jnz     loc_180071A3D
0x180071900  lea     rdx, [rsp+4D0h+KeyHandle]; KeyHandle
0x180071905  mov     ecx, 2000000h; DesiredAccess
0x18007190a  call    cs:__imp_RtlOpenCurrentUser
0x180071910  test    eax, eax
0x180071912  js      loc_1800719A9
0x180071918  mov     r8d, 200h
0x18007191e  mov     [rbp+3D0h+ApiMessage], r15w
0x180071923  mov     ecx, r8d
0x180071926  lea     rax, [rbp+3D0h+ApiMessage]
0x18007192a  nop     word ptr [rax+rax+00h]
0x180071930  cmp     [rax], r15w
0x180071934  jz      short loc_18007193F
0x180071936  add     rax, r12
0x180071939  sub     rcx, 1
0x18007193d  jnz     short loc_180071930
0x18007193f  mov     r9, r8
0x180071942  sub     r9, rcx
0x180071945  test    rcx, rcx
0x180071948  cmovz   r9, r15
0x18007194c  jz      short loc_180071999
0x18007194e  sub     r8, r9
0x180071951  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x180071958  lea     r9, [rbp+r9*2+3D0h+ApiMessage]
0x18007195d  mov     ecx, 7FFFFFFEh
0x180071962  jz      short loc_180071984
0x180071964  test    rcx, rcx
0x180071967  jz      short loc_180071984
0x180071969  movzx   eax, word ptr [rdx]
0x18007196c  test    ax, ax
0x18007196f  jz      short loc_180071984
0x180071971  mov     [r9], ax
0x180071975  add     rdx, r12
0x180071978  add     r9, r12
0x18007197b  dec     rcx
0x18007197e  sub     r8, 1
0x180071982  jnz     short loc_180071964
0x180071984  test    r8, r8
0x180071987  lea     rcx, [r9-2]
0x18007198b  cmovnz  rcx, r9
0x18007198f  mov     [rcx], r15w
0x180071993  jnz     loc_180071A9F
0x180071999  mov     rcx, [rsp+4D0h+KeyHandle]; Handle
0x18007199e  test    rcx, rcx
0x1800719a1  jz      short loc_1800719A9
0x1800719a3  call    cs:__imp_NtClose
0x1800719a9  mov     ecx, 3F1h; dwErrCode
0x1800719ae  call    SetLastError_0
0x1800719b3  jmp     loc_180071657
0x1800719b8  mov     edx, [rax+0D8h]
0x1800719be  mov     rcx, cs:qword_18039EC90
0x1800719c5  test    edx, edx
0x1800719c7  jz      short loc_1800719DB
0x1800719c9  and     edi, 0Fh
0x1800719cc  lea     rdx, [rdx+rdi*2]
0x1800719d0  mov     eax, [rcx+rdx*2-2]
0x1800719d4  lea     rcx, [rcx+rax*2]
0x1800719d8  add     rcx, r12
0x1800719db  test    rcx, rcx
0x1800719de  jz      short loc_1800719EA
0x1800719e0  cmp     [rcx], r15w
0x1800719e4  jnz     loc_18007178F
0x1800719ea  mov     cs:gpSysLocHashN, r15
0x1800719f1  jmp     loc_1800717A2
0x1800719f6  mov     rdx, [rdx+58h]
0x1800719fa  test    rdx, rdx
0x1800719fd  jnz     loc_180071727
0x180071a03  jmp     loc_18007172F
0x180071a08  call    Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline
0x180071a0d  test    eax, eax
0x180071a0f  jnz     short loc_1800719EA
0x180071a11  call    Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline
0x180071a16  test    eax, eax
0x180071a18  jnz     short loc_180071A56
0x180071a1a  call    CreateTransientLocales
0x180071a1f  test    eax, eax
0x180071a21  jnz     short loc_180071A56
0x180071a23  mov     rax, r15
0x180071a26  jmp     loc_180071796
0x180071a2b  xor     r9d, r9d
0x180071a2e  mov     edx, edi
0x180071a30  mov     rcx, rax
0x180071a33  call    MakeLocHashNodeFromSystemLocale
0x180071a38  jmp     loc_180071796
0x180071a3d  sub     eax, r12d
0x180071a40  jnz     short loc_180071A62
0x180071a42  lea     rdx, [rsp+4D0h+KeyHandle]; KeyHandle
0x180071a47  mov     ecx, 2000000h; DesiredAccess
0x180071a4c  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180071a51  jmp     loc_180071910
0x180071a56  mov     ecx, edi
0x180071a58  call    FindLocaleHashNode
0x180071a5d  jmp     loc_180071796
0x180071a62  cmp     eax, 1
0x180071a65  jnz     loc_1800719A9
0x180071a6b  lea     r9, [rsp+4D0h+var_47C]
0x180071a70  mov     [rsp+4D0h+var_47C], r15d
0x180071a75  lea     r8, [rsp+4D0h+KeyHandle]; KeyHandle
0x180071a7a  xor     edx, edx; Sid
0x180071a7c  mov     ecx, 2000000h; DesiredAccess
0x180071a81  call    OpenGlobalizationUserSettingsKey_ForMua
0x180071a86  jmp     loc_180071910
0x180071a8b  mov     edx, 20019h; DesiredAccess
0x180071a90  lea     rcx, [rsp+4D0h+Handle]; KeyHandle
0x180071a95  call    OpenRegistryInternationalKey
  ... truncated ...
```
