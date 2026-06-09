# NetrWkstaGetInfo

- ea: `0x180008df0`
- end: `0x1800092b3`
- name: `NetrWkstaGetInfo`
- size: `1219`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005a60`
- `0x180008df0`
- `0x18001ed3a`
- `0x18001ed46`
- `0x18002ab1c`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180008f4c`
- `ntdll!RtlAcquireResourceShared` at `0x180008f4c`
- `ntdll!RtlNtStatusToDosError` at `0x180009237`
- `ntdll!RtlNtStatusToDosError` at `0x180009237`
- `ntdll!RtlReleaseResource` at `0x18000922f`
- `ntdll!RtlReleaseResource` at `0x180009246`
- `ntdll!RtlReleaseResource` at `0x18000922f`
- `ntdll!RtlReleaseResource` at `0x180009246`
- `ntdll!RtlAdjustPrivilege` at `0x180008eb4`
- `ntdll!RtlAdjustPrivilege` at `0x180008eb4`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180008f1f`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180008f1f`
- `ntdll!RtlInitUnicodeString` at `0x180008e72`
- `ntdll!RtlInitUnicodeString` at `0x180008e87`
- `ntdll!RtlInitUnicodeString` at `0x180008e9c`
- `ntdll!RtlInitUnicodeString` at `0x180008e72`
- `ntdll!RtlInitUnicodeString` at `0x180008e87`
- `ntdll!RtlInitUnicodeString` at `0x180008e9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009058`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009058`
- `RPCRT4!RpcImpersonateClient` at `0x180008ebc`
- `RPCRT4!RpcImpersonateClient` at `0x180008ebc`
- `RPCRT4!RpcRevertToSelf` at `0x180008f27`
- `RPCRT4!RpcRevertToSelf` at `0x180008f27`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180008fc4`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180008fc4`
- `SspiCli!LsaFreeReturnBuffer` at `0x180008ff3`
- `SspiCli!LsaFreeReturnBuffer` at `0x180008ff3`

## string_xrefs

- `0x180008e78`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaGetInfo(__int64 a1, int a2, _QWORD *a3)
{
  int v5; // r14d
  ACCESS_MASK DesiredAccess; // edi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rsi
  NTSTATUS v8; // edi
  _DWORD *v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // ecx
  unsigned int v13; // eax
  __int64 v14; // r12
  _DWORD *v15; // rax
  unsigned __int64 v16; // r13
  _WORD *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // rdx
  _WORD *v21; // rbx
  __int64 v22; // rdi
  unsigned int PlatformInfo; // edi
  int v24; // ebx
  _WORD *v25; // rcx
  DWORD ReturnBufferLength; // [rsp+60h] [rbp-88h] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+68h] [rbp-80h] BYREF
  int v29; // [rsp+70h] [rbp-78h]
  _WORD *v30; // [rsp+78h] [rbp-70h]
  struct _UNICODE_STRING ObjectName; // [rsp+80h] [rbp-68h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+90h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-48h] BYREF
  HLOCAL v34; // [rsp+B0h] [rbp-38h]
  int OldValue; // [rsp+F8h] [rbp+10h] BYREF
  unsigned int GenerateOnClose; // [rsp+108h] [rbp+20h] BYREF

  switch ( a2 )
  {
    case 100:
      v5 = 1;
      DesiredAccess = 1;
      break;
    case 101:
      DesiredAccess = 2;
      v5 = 1;
      break;
    case 102:
    case 502:
      DesiredAccess = 4;
      v5 = 1;
      break;
    default:
      return 124;
  }
  SecurityDescriptor = ConfigurationInfoSd;
  LOBYTE(OldValue) = 0;
  DestinationString = 0;
  ObjectTypeName = 0;
  ObjectName = 0;
  ReturnBufferLength = 0;
  LOBYTE(GenerateOnClose) = 0;
  LODWORD(ProtocolReturnBuffer) = 0;
  RtlInitUnicodeString(&DestinationString, L"Workstation");
  RtlInitUnicodeString(&ObjectTypeName, L"WkstaConfigurationInfo");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&OldValue);
  if ( RpcImpersonateClient(0) )
    return 5;
  v8 = NtAccessCheckAndAuditAlarm(
         &DestinationString,
         0,
         &ObjectTypeName,
         &ObjectName,
         SecurityDescriptor,
         DesiredAccess,
         &WsConfigInfoMapping,
         0,
         &ReturnBufferLength,
         (PNTSTATUS)&ProtocolReturnBuffer,
         (PBOOLEAN)&GenerateOnClose);
  RpcRevertToSelf();
  if ( v8 < 0 || (_DWORD)ProtocolReturnBuffer )
    return 5;
  v9 = 0;
  if ( RtlAcquireResourceShared(&WsInfo, 1u) )
  {
    if ( a2 == 102 )
    {
      ProtocolReturnBuffer = 0;
      GenerateOnClose = 0;
      ReturnBufferLength = 0;
      OldValue = 2;
      v10 = LsaCallAuthenticationPackage(
              LsaHandle,
              AuthenticationPackage,
              &OldValue,
              4u,
              &ProtocolReturnBuffer,
              &ReturnBufferLength,
              (PNTSTATUS)&GenerateOnClose);
      if ( v10 || (v10 = GenerateOnClose) != 0 )
      {
        PlatformInfo = WsMapStatus(v10);
        if ( PlatformInfo )
          goto LABEL_28;
      }
      if ( !ProtocolReturnBuffer )
      {
        PlatformInfo = 31;
        goto LABEL_28;
      }
      v5 = *((_DWORD *)ProtocolReturnBuffer + 1);
      LsaFreeReturnBuffer(ProtocolReturnBuffer);
    }
    else if ( a2 != 100 && a2 != 101 )
    {
      if ( a2 == 502 )
      {
        PlatformInfo = WsGetPlatformInfo(502, a3);
        v29 = PlatformInfo;
      }
      else
      {
        PlatformInfo = 124;
        v29 = 124;
      }
      goto LABEL_50;
    }
    v30 = 0;
    v11 = 48;
    if ( a2 != 102 )
      v11 = 40;
    if ( (unsigned int)(2 * (dword_18004EF4C + dword_18004EF70)) >> 1 < dword_18004EF4C )
    {
      PlatformInfo = 8;
    }
    else
    {
      v12 = 2 * (dword_18004EF4C + dword_18004EF70) + 6;
      if ( v12 < 6 )
      {
        PlatformInfo = 8;
      }
      else
      {
        v13 = v11 + v12;
        if ( v11 + v12 < v11 )
        {
          PlatformInfo = 8;
        }
        else
        {
          v14 = v13;
          v15 = LocalAlloc(0x40u, v13);
          v9 = v15;
          v34 = v15;
          if ( v15 )
          {
            memset_0(v15, 0, (unsigned int)v14);
            v16 = (unsigned __int64)&v9[v11 / 4];
            v17 = (_WORD *)((char *)v9 + v14);
            v30 = (_WORD *)((char *)v9 + v14);
            if ( a2 != 100 )
            {
              v24 = a2 - 101;
              if ( v24 )
              {
                if ( v24 != 1 )
                {
LABEL_27:
                  PlatformInfo = 0;
                  goto LABEL_28;
                }
                v9[10] = v5;
              }
              v25 = v17 - 1;
              if ( (unsigned __int64)(v17 - 1) < v16 )
              {
                *((_QWORD *)v9 + 4) = 0;
              }
              else
              {
                --v17;
                v30 = v25;
                *v25 = 0;
                *((_QWORD *)v9 + 4) = v25;
              }
            }
            *v9 = dword_18004EF74;
            v9[6] = dword_18004EF78;
            v9[7] = dword_18004EF7C;
            v18 = (unsigned int)(dword_18004EF4C + 1);
            if ( (unsigned __int64)&v17[-v18] < v16 )
            {
              *((_QWORD *)v9 + 1) = 0;
            }
            else
            {
              v17 -= (unsigned int)v18;
              v30 = v17;
              v19 = (unsigned int)dword_18004EF4C;
              if ( dword_18004EF4C )
                o_wcsncpy_s_0(v17, v18, qword_18004ED40, (unsigned int)dword_18004EF4C);
              v17[v19] = 0;
              *((_QWORD *)v9 + 1) = v17;
            }
            v20 = (unsigned int)(dword_18004EF70 + 1);
            if ( (unsigned __int64)&v17[-v20] < v16 )
            {
              *((_QWORD *)v9 + 2) = 0;
            }
            else
            {
              v21 = &v17[-(unsigned int)v20];
              v30 = v21;
              v22 = (unsigned int)dword_18004EF70;
              if ( dword_18004EF70 )
                o_wcsncpy_s_0(v21, v20, &word_18004EF50, (unsigned int)dword_18004EF70);
              v21[v22] = 0;
              *((_QWORD *)v9 + 2) = v21;
            }
            goto LABEL_27;
          }
          PlatformInfo = 8;
        }
      }
    }
LABEL_28:
    v29 = PlatformInfo;
    if ( !PlatformInfo )
      *a3 = v9;
LABEL_50:
    RtlReleaseResource(&WsInfo);
    return PlatformInfo;
  }
  return 2140;
}

```

## disassembly

```asm
0x180008df0  mov     [rsp+arg_0], rbx
0x180008df5  mov     [rsp+arg_10], rsi
0x180008dfa  push    rdi
0x180008dfb  push    r12
0x180008dfd  push    r13
0x180008dff  push    r14
0x180008e01  push    r15
0x180008e03  sub     rsp, 0C0h
0x180008e0a  mov     r15, r8
0x180008e0d  mov     ebx, edx
0x180008e0f  cmp     edx, 64h ; 'd'
0x180008e12  jnz     loc_18000926B
0x180008e18  mov     r14d, 1
0x180008e1e  mov     edi, r14d
0x180008e21  mov     rsi, cs:ConfigurationInfoSd
0x180008e28  mov     byte ptr [rsp+0E8h+OldValue], 0
0x180008e30  xorps   xmm0, xmm0
0x180008e33  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x180008e3b  xorps   xmm1, xmm1
0x180008e3e  movups  xmmword ptr [rsp+0E8h+ObjectTypeName.Length], xmm1
0x180008e46  movups  xmmword ptr [rsp+0E8h+ObjectName.Length], xmm0
0x180008e4e  xor     r12d, r12d
0x180008e51  mov     [rsp+0E8h+ReturnBufferLength], r12d
0x180008e56  mov     byte ptr [rsp+0E8h+arg_18], r12b
0x180008e5e  mov     dword ptr [rsp+0E8h+ProtocolReturnBuffer], r12d
0x180008e63  lea     rdx, SourceName; "Workstation"
0x180008e6a  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x180008e72  call    cs:__imp_RtlInitUnicodeString
0x180008e78  lea     rdx, aWkstaconfigura; "WkstaConfigurationInfo"
0x180008e7f  lea     rcx, [rsp+0E8h+ObjectTypeName]; DestinationString
0x180008e87  call    cs:__imp_RtlInitUnicodeString
0x180008e8d  lea     rdx, asc_18003AB90; "-"
0x180008e94  lea     rcx, [rsp+0E8h+ObjectName]; DestinationString
0x180008e9c  call    cs:__imp_RtlInitUnicodeString
0x180008ea2  lea     r9, [rsp+0E8h+OldValue]; OldValue
0x180008eaa  xor     r8d, r8d; ForThread
0x180008ead  mov     dl, 1; NewValue
0x180008eaf  mov     ecx, 15h; Privilege
0x180008eb4  call    cs:__imp_RtlAdjustPrivilege
0x180008eba  xor     ecx, ecx; BindingHandle
0x180008ebc  call    cs:__imp_RpcImpersonateClient
0x180008ec2  test    eax, eax
0x180008ec4  jnz     loc_18000928E
0x180008eca  lea     rax, [rsp+0E8h+arg_18]
0x180008ed2  mov     [rsp+0E8h+GenerateOnClose], rax; GenerateOnClose
0x180008ed7  lea     rax, [rsp+0E8h+ProtocolReturnBuffer]
0x180008edc  mov     [rsp+0E8h+AccessStatus], rax; AccessStatus
0x180008ee1  lea     rax, [rsp+0E8h+ReturnBufferLength]
0x180008ee6  mov     [rsp+0E8h+GrantedAccess], rax; GrantedAccess
0x180008eeb  mov     [rsp+0E8h+ObjectCreation], r12b; ObjectCreation
0x180008ef0  lea     rax, WsConfigInfoMapping
0x180008ef7  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x180008efc  mov     [rsp+0E8h+DesiredAccess], edi; DesiredAccess
0x180008f00  mov     [rsp+0E8h+SecurityDescriptor], rsi; SecurityDescriptor
0x180008f05  lea     r9, [rsp+0E8h+ObjectName]; ObjectName
0x180008f0d  lea     r8, [rsp+0E8h+ObjectTypeName]; ObjectTypeName
0x180008f15  xor     edx, edx; HandleId
0x180008f17  lea     rcx, [rsp+0E8h+DestinationString]; SubsystemName
0x180008f1f  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180008f25  mov     edi, eax
0x180008f27  call    cs:__imp_RpcRevertToSelf
0x180008f2d  test    edi, edi
0x180008f2f  js      loc_18000928E
0x180008f35  cmp     dword ptr [rsp+0E8h+ProtocolReturnBuffer], r12d
0x180008f3a  jnz     loc_18000928E
0x180008f40  mov     esi, r12d
0x180008f43  mov     dl, 1; Wait
0x180008f45  lea     rcx, WsInfo; Resource
0x180008f4c  call    cs:__imp_RtlAcquireResourceShared
0x180008f52  test    al, al
0x180008f54  jz      loc_18000929C
0x180008f5a  cmp     ebx, 66h ; 'f'
0x180008f5d  jnz     loc_1800091BF
0x180008f63  mov     [rsp+0E8h+ProtocolReturnBuffer], r12
0x180008f68  mov     [rsp+0E8h+arg_18], r12d
0x180008f70  mov     [rsp+0E8h+OldValue], r12d
0x180008f78  mov     [rsp+0E8h+ReturnBufferLength], r12d
0x180008f7d  mov     [rsp+0E8h+OldValue], 2
0x180008f88  lea     rax, [rsp+0E8h+arg_18]
0x180008f90  mov     [rsp+0E8h+GenericMapping], rax; ProtocolStatus
0x180008f95  lea     rax, [rsp+0E8h+ReturnBufferLength]
0x180008f9a  mov     qword ptr [rsp+0E8h+DesiredAccess], rax; ReturnBufferLength
0x180008f9f  lea     rax, [rsp+0E8h+ProtocolReturnBuffer]
0x180008fa4  mov     [rsp+0E8h+SecurityDescriptor], rax; ProtocolReturnBuffer
0x180008fa9  mov     r9d, 4; SubmitBufferLength
0x180008faf  lea     r8, [rsp+0E8h+OldValue]; ProtocolSubmitBuffer
0x180008fb7  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x180008fbd  mov     rcx, cs:LsaHandle; LsaHandle
0x180008fc4  call    cs:__imp_LsaCallAuthenticationPackage
0x180008fca  test    eax, eax
0x180008fcc  jnz     loc_1800091FA
0x180008fd2  mov     eax, [rsp+0E8h+arg_18]
0x180008fd9  test    eax, eax
0x180008fdb  jnz     loc_1800091FA
0x180008fe1  mov     rcx, [rsp+0E8h+ProtocolReturnBuffer]; Buffer
0x180008fe6  test    rcx, rcx
0x180008fe9  jz      loc_180009210
0x180008fef  mov     r14d, [rcx+4]
0x180008ff3  call    cs:__imp_LsaFreeReturnBuffer
0x180008ff9  jmp     short loc_180009004
0x180008ffb  cmp     ebx, 66h ; 'f'
0x180008ffe  jz      loc_180008F63
0x180009004  mov     [rsp+0E8h+var_70], r12
0x180009009  mov     edi, 30h ; '0'
0x18000900e  mov     eax, 28h ; '('
0x180009013  cmp     ebx, 66h ; 'f'
0x180009016  cmovnz  edi, eax
0x180009019  mov     ecx, cs:dword_18004EF70
0x18000901f  add     ecx, cs:dword_18004EF4C
0x180009025  add     ecx, ecx
0x180009027  mov     eax, ecx
0x180009029  shr     eax, 1
0x18000902b  cmp     eax, cs:dword_18004EF4C
0x180009031  jb      loc_180009159
0x180009037  add     ecx, 6
0x18000903a  cmp     ecx, 6
0x18000903d  jb      loc_18000921A
0x180009043  lea     eax, [rdi+rcx]
0x180009046  cmp     eax, edi
0x180009048  jb      loc_1800091AB
0x18000904e  mov     r12d, eax
0x180009051  mov     edx, eax; uBytes
0x180009053  mov     ecx, 40h ; '@'; uFlags
0x180009058  call    cs:__imp_LocalAlloc
0x18000905e  mov     rsi, rax
0x180009061  mov     [rsp+0E8h+var_38], rax
0x180009069  test    rax, rax
0x18000906c  jz      loc_18000918D
0x180009072  mov     r8d, r12d; Size
0x180009075  xor     edx, edx; Val
0x180009077  mov     rcx, rax; void *
0x18000907a  call    memset_0
0x18000907f  mov     r13d, edi
0x180009082  add     r13, rsi
0x180009085  lea     rdi, [r12+rsi]
0x180009089  mov     [rsp+0E8h+var_70], rdi
0x18000908e  cmp     ebx, 64h ; 'd'
0x180009091  jnz     loc_180009160
0x180009097  mov     eax, cs:dword_18004EF74
0x18000909d  mov     [rsi], eax
0x18000909f  mov     eax, cs:dword_18004EF78
0x1800090a5  mov     [rsi+18h], eax
0x1800090a8  mov     eax, cs:dword_18004EF7C
0x1800090ae  mov     [rsi+1Ch], eax
0x1800090b1  mov     ecx, cs:dword_18004EF4C
0x1800090b7  lea     edx, [rcx+1]
0x1800090ba  imul    rax, rdx, -2
0x1800090be  add     rax, rdi
0x1800090c1  cmp     rax, r13
0x1800090c4  jb      loc_180009194
0x1800090ca  mov     eax, edx
0x1800090cc  neg     rax
0x1800090cf  lea     rdi, [rdi+rax*2]
0x1800090d3  mov     [rsp+0E8h+var_70], rdi
0x1800090d8  mov     ebx, ecx
0x1800090da  test    ecx, ecx
0x1800090dc  jz      short loc_1800090F0
0x1800090de  mov     r9d, ecx
0x1800090e1  lea     r8, qword_18004ED40
0x1800090e8  mov     rcx, rdi
0x1800090eb  call    _o_wcsncpy_s_0
0x1800090f0  xor     eax, eax
0x1800090f2  mov     [rdi+rbx*2], ax
0x1800090f6  mov     [rsi+8], rdi
0x1800090fa  mov     ecx, cs:dword_18004EF70
0x180009100  lea     edx, [rcx+1]
0x180009103  imul    rax, rdx, -2
0x180009107  add     rax, rdi
0x18000910a  cmp     rax, r13
0x18000910d  jb      loc_1800091A1
0x180009113  mov     eax, edx
0x180009115  neg     rax
0x180009118  lea     rbx, [rdi+rax*2]
0x18000911c  mov     [rsp+0E8h+var_70], rbx
0x180009121  mov     edi, ecx
0x180009123  test    ecx, ecx
0x180009125  jz      short loc_180009139
0x180009127  mov     r9d, ecx
0x18000912a  lea     r8, word_18004EF50
0x180009131  mov     rcx, rbx
0x180009134  call    _o_wcsncpy_s_0
0x180009139  xor     eax, eax
0x18000913b  mov     [rbx+rdi*2], ax
0x18000913f  mov     [rsi+10h], rbx
0x180009143  xor     edi, edi
0x180009145  mov     [rsp+0E8h+var_78], edi
0x180009149  test    edi, edi
0x18000914b  jnz     loc_180009224
0x180009151  mov     [r15], rsi
0x180009154  jmp     loc_180009224
0x180009159  mov     edi, 8
0x18000915e  jmp     short loc_180009145
0x180009160  sub     ebx, 65h ; 'e'
0x180009163  jz      short loc_18000916E
0x180009165  cmp     ebx, 1
0x180009168  jnz     short loc_180009143
0x18000916a  mov     [rsi+28h], r14d
0x18000916e  lea     rcx, [rdi-2]
0x180009172  cmp     rcx, r13
0x180009175  jb      short loc_1800091B2
0x180009177  mov     rdi, rcx
0x18000917a  mov     [rsp+0E8h+var_70], rcx
0x18000917f  xor     eax, eax
0x180009181  mov     [rcx], ax
0x180009184  mov     [rsi+20h], rcx
0x180009188  jmp     loc_180009097
0x18000918d  mov     edi, 8
0x180009192  jmp     short loc_180009145
0x180009194  mov     qword ptr [rsi+8], 0
0x18000919c  jmp     loc_1800090FA
0x1800091a1  mov     qword ptr [rsi+10h], 0
0x1800091a9  jmp     short loc_180009143
0x1800091ab  mov     edi, 8
0x1800091b0  jmp     short loc_180009145
0x1800091b2  mov     qword ptr [rsi+20h], 0
0x1800091ba  jmp     loc_180009097
0x1800091bf  mov     eax, ebx
0x1800091c1  sub     eax, 64h ; 'd'
0x1800091c4  jz      loc_180008FFB
0x1800091ca  sub     eax, 1
0x1800091cd  jz      loc_180008FFB
0x1800091d3  cmp     eax, 191h
0x1800091d8  jz      short loc_1800091E5
0x1800091da  mov     edi, 7Ch ; '|'
0x1800091df  mov     [rsp+0E8h+var_78], edi
0x1800091e3  jmp     short loc_180009224
0x1800091e5  mov     rdx, r15
0x1800091e8  mov     ecx, 1F6h
0x1800091ed  call    WsGetPlatformInfo
0x1800091f2  mov     edi, eax
0x1800091f4  mov     [rsp+0E8h+var_78], eax
0x1800091f8  jmp     short loc_180009224
0x1800091fa  mov     ecx, eax
0x1800091fc  call    WsMapStatus
0x180009201  mov     edi, eax
0x180009203  test    eax, eax
0x180009205  jnz     loc_180009145
0x18000920b  jmp     loc_180008FE1
0x180009210  mov     edi, 1Fh
0x180009215  jmp     loc_180009145
0x18000921a  mov     edi, 8
0x18000921f  jmp     loc_180009145
0x180009224  jmp     short loc_18000923F
0x180009226  mov     ebx, eax
0x180009228  lea     rcx, WsInfo; Resource
0x18000922f  call    cs:__imp_RtlReleaseResource
0x180009235  mov     ecx, ebx; Status
0x180009237  call    cs:__imp_RtlNtStatusToDosError
0x18000923d  jmp     short loc_18000924E
0x18000923f  lea     rcx, WsInfo; Resource
0x180009246  call    cs:__imp_RtlReleaseResource
0x18000924c  mov     eax, edi
0x18000924e  lea     r11, [rsp+0E8h+var_28]
0x180009256  mov     rbx, [r11+30h]
0x18000925a  mov     rsi, [r11+40h]
0x18000925e  mov     rsp, r11
0x180009261  pop     r15
0x180009263  pop     r14
0x180009265  pop     r13
0x180009267  pop     r12
0x180009269  pop     rdi
0x18000926a  retn
0x18000926b  mov     eax, ebx
0x18000926d  sub     eax, 65h ; 'e'
0x180009270  jz      short loc_1800092A3
0x180009272  sub     eax, 1
0x180009275  jz      short loc_18000927E
0x180009277  cmp     eax, 190h
0x18000927c  jnz     short loc_180009295
0x18000927e  mov     edi, 4
0x180009283  mov     r14d, 1
0x180009289  jmp     loc_180008E21
0x18000928e  mov     eax, 5
0x180009293  jmp     short loc_18000924E
0x180009295  mov     eax, 7Ch ; '|'
0x18000929a  jmp     short loc_18000924E
0x18000929c  mov     eax, 85Ch
0x1800092a1  jmp     short loc_18000924E
0x1800092a3  mov     edi, 2
0x1800092a8  mov     r14d, 1
0x1800092ae  jmp     loc_180008E21
```
