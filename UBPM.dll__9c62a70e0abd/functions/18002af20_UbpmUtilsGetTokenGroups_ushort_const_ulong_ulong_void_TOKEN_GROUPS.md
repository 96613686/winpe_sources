# UbpmUtilsGetTokenGroups(ushort const *,ulong,ulong,void * *,_TOKEN_GROUPS * *)

- ea: `0x18002af20`
- end: `0x18002b262`
- name: `?UbpmUtilsGetTokenGroups@@YAKPEBGKKPEAPEAXPEAPEAU_TOKEN_GROUPS@@@Z`
- size: `834`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int, void **, struct _TOKEN_GROUPS **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f284`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18002af20`
- `0x18002b3a8`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b070`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b082`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b140`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b070`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b082`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002b140`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b196`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b1ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b196`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b1ab`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18002afb8`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18002afb8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002b15b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002b204`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002b15b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002b204`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b005`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b04c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b005`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b214`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetTokenGroups(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int a3,
        void **a4,
        struct _TOKEN_GROUPS **a5)
{
  struct _TOKEN_GROUPS **v6; // r8
  struct _TOKEN_GROUPS *v7; // rsi
  void *v8; // r12
  DWORD v9; // edi
  DWORD LengthSid; // ebx
  DWORD v11; // ebx
  DWORD v12; // r14d
  struct _TOKEN_GROUPS *v13; // rax
  char *v14; // rbx
  unsigned int v15; // r14d
  char *v16; // r15
  __int64 v17; // rcx
  struct _TOKEN_GROUPS *v18; // rax
  unsigned int i; // r13d
  __int64 v20; // rdi
  void *v21; // rcx
  DWORD v22; // eax
  void *v23; // r8
  PSID Sid; // rdx
  DWORD LastError; // ebx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int ConsumerSid; // eax
  unsigned int v31; // [rsp+60h] [rbp-51h] BYREF
  PSID pSid; // [rsp+68h] [rbp-49h] BYREF
  void *v33; // [rsp+70h] [rbp-41h] BYREF
  struct _LUID Luid; // [rsp+78h] [rbp-39h] BYREF
  PSID v35; // [rsp+80h] [rbp-31h] BYREF
  void **v36; // [rsp+88h] [rbp-29h]
  struct _TOKEN_GROUPS **v37; // [rsp+90h] [rbp-21h]
  PSID pSourceSid; // [rsp+98h] [rbp-19h]
  _DWORD v39[2]; // [rsp+A0h] [rbp-11h]
  PSID v40; // [rsp+A8h] [rbp-9h]
  int v41; // [rsp+B0h] [rbp-1h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v43; // [rsp+C0h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v6 = a5;
  v37 = a5;
  v7 = 0;
  v36 = a4;
  v8 = 0;
  *(_DWORD *)v43.Value = 0;
  v9 = 0;
  *(_WORD *)&v43.Value[4] = 512;
  v39[0] = -1073741817;
  v41 = 7;
  pSid = 0;
  v33 = 0;
  v31 = 0;
  v35 = 0;
  Luid = 0;
  if ( a3 > 0x400 )
  {
    LastError = 1389;
    goto LABEL_20;
  }
  if ( !a4 )
  {
    ConsumerSid = UbpmUtilsGetConsumerSid(a1, a2, &v33, &v31);
    v8 = v33;
    LastError = ConsumerSid;
    if ( ConsumerSid )
      goto LABEL_16;
    v9 = v31;
  }
  if ( AllocateLocallyUniqueId(&Luid) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 3u, 5u, Luid.HighPart, Luid.LowPart, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( AllocateAndInitializeSid(&v43, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v35) )
      {
        pSourceSid = pSid;
        v40 = v35;
        LengthSid = GetLengthSid(v35);
        v11 = GetLengthSid(pSid) + LengthSid;
        v12 = v9 + v11 + 16 * ((v8 != 0) + a3) + 40;
        v13 = (struct _TOKEN_GROUPS *)UbpmAlloc(v12);
        v7 = v13;
        if ( v13 )
        {
          v14 = (char *)v13 + v12 - (unsigned __int64)(v11 + v9);
          v13->GroupCount = a3 + (v8 != 0) + 2;
          if ( !v8 )
          {
            v15 = 0;
            v16 = v14;
            if ( a3 )
            {
              v6 = (struct _TOKEN_GROUPS **)v36;
              a2 = 0;
              do
              {
                ++v15;
                v17 = a2;
                v7->Groups[v17].Attributes = 14;
                v18 = v6[a2++];
                v7->Groups[v17].Sid = v18;
              }
              while ( v15 < a3 );
            }
LABEL_11:
            for ( i = 0; i < 2; ++i )
            {
              v20 = v15;
              v21 = *(void **)&v39[4 * i - 2];
              v7->Groups[v20].Attributes = v39[4 * i];
              v7->Groups[v20].Sid = v16;
              v22 = GetLengthSid(v21);
              v23 = *(void **)&v39[4 * i - 2];
              Sid = v7->Groups[v15].Sid;
              v31 = v22;
              if ( !CopySid(v22, Sid, v23) )
                goto LABEL_22;
              v16 += v31;
              ++v15;
            }
            LastError = 0;
            *v37 = v7;
            v7 = 0;
            goto LABEL_16;
          }
          v13->Groups[0].Attributes = 14;
          v13->Groups[0].Sid = v14;
          if ( CopySid(v9, v14, v8) )
          {
            v15 = 1;
            v16 = &v14[v9];
            goto LABEL_11;
          }
        }
      }
    }
  }
LABEL_22:
  LastError = GetLastError();
LABEL_16:
  if ( pSid )
    FreeSid(pSid);
  if ( v35 )
    FreeSid(v35);
LABEL_20:
  UBPM_MIDL_user_free(v7, a2, v6, a4);
  UBPM_MIDL_user_free(v8, v26, v27, v28);
  return LastError;
}

```

## disassembly

```asm
0x18002af20  mov     [rsp-8+arg_18], rbx
0x18002af25  push    rbp
0x18002af26  push    rsi
0x18002af27  push    rdi
0x18002af28  push    r12
0x18002af2a  push    r13
0x18002af2c  push    r14
0x18002af2e  push    r15
0x18002af30  lea     rbp, [rsp-1Fh]
0x18002af35  sub     rsp, 0D0h
0x18002af3c  mov     rax, cs:__security_cookie
0x18002af43  xor     rax, rsp
0x18002af46  mov     [rbp+4Fh+var_38], rax
0x18002af4a  xor     r15d, r15d
0x18002af4d  mov     word ptr [rbp+4Fh+pIdentifierAuthority.Value+4], 500h
0x18002af53  mov     r13d, r8d
0x18002af56  mov     dword ptr [rbp+4Fh+pIdentifierAuthority.Value], r15d
0x18002af5a  mov     r8, [rbp+4Fh+arg_20]
0x18002af5e  mov     rax, r9
0x18002af61  mov     [rbp+4Fh+var_70], r8
0x18002af65  mov     esi, r15d
0x18002af68  mov     [rbp+4Fh+var_78], rax
0x18002af6c  mov     r12d, r15d
0x18002af6f  mov     dword ptr [rbp+4Fh+var_40.Value], r15d
0x18002af73  mov     edi, r15d
0x18002af76  mov     word ptr [rbp+4Fh+var_40.Value+4], 200h
0x18002af7c  mov     [rbp+4Fh+var_60], 0C0000007h
0x18002af83  mov     [rbp+4Fh+var_50], 7
0x18002af8a  mov     [rbp+4Fh+var_98], r15
0x18002af8e  mov     [rbp+4Fh+var_90], r15
0x18002af92  mov     [rbp+4Fh+var_A0], r15d
0x18002af96  mov     [rbp+4Fh+var_80], r15
0x18002af9a  mov     qword ptr [rbp+4Fh+Luid.LowPart], r15
0x18002af9e  cmp     r13d, 400h
0x18002afa5  ja      loc_18002B227
0x18002afab  test    rax, rax
0x18002afae  jz      loc_18002B22E
0x18002afb4  lea     rcx, [rbp+4Fh+Luid]; Luid
0x18002afb8  call    cs:__imp_AllocateLocallyUniqueId
0x18002afbf  nop     dword ptr [rax+rax+00h]
0x18002afc4  test    eax, eax
0x18002afc6  jz      loc_18002B214
0x18002afcc  mov     r9d, [rbp+4Fh+Luid.HighPart]; nSubAuthority1
0x18002afd0  lea     rax, [rbp+4Fh+var_98]
0x18002afd4  mov     [rsp+100h+pSid], rax; pSid
0x18002afd9  lea     rcx, [rbp+4Fh+pIdentifierAuthority]; pIdentifierAuthority
0x18002afdd  mov     eax, [rbp+4Fh+Luid.LowPart]
0x18002afe0  mov     r8d, 5; nSubAuthority0
0x18002afe6  mov     [rsp+100h+nSubAuthority7], r15d; nSubAuthority7
0x18002afeb  mov     dl, 3; nSubAuthorityCount
0x18002afed  mov     [rsp+100h+nSubAuthority6], r15d; nSubAuthority6
0x18002aff2  mov     [rsp+100h+nSubAuthority5], r15d; nSubAuthority5
0x18002aff7  mov     [rsp+100h+nSubAuthority4], r15d; nSubAuthority4
0x18002affc  mov     [rsp+100h+nSubAuthority3], r15d; nSubAuthority3
0x18002b001  mov     [rsp+100h+nSubAuthority2], eax; nSubAuthority2
0x18002b005  call    cs:__imp_AllocateAndInitializeSid
0x18002b00c  nop     dword ptr [rax+rax+00h]
0x18002b011  test    eax, eax
0x18002b013  jz      loc_18002B214
0x18002b019  lea     rax, [rbp+4Fh+var_80]
0x18002b01d  xor     r9d, r9d; nSubAuthority1
0x18002b020  mov     [rsp+100h+pSid], rax; pSid
0x18002b025  lea     rcx, [rbp+4Fh+var_40]; pIdentifierAuthority
0x18002b029  mov     [rsp+100h+nSubAuthority7], r15d; nSubAuthority7
0x18002b02e  xor     r8d, r8d; nSubAuthority0
0x18002b031  mov     [rsp+100h+nSubAuthority6], r15d; nSubAuthority6
0x18002b036  mov     dl, 1; nSubAuthorityCount
0x18002b038  mov     [rsp+100h+nSubAuthority5], r15d; nSubAuthority5
0x18002b03d  mov     [rsp+100h+nSubAuthority4], r15d; nSubAuthority4
0x18002b042  mov     [rsp+100h+nSubAuthority3], r15d; nSubAuthority3
0x18002b047  mov     [rsp+100h+nSubAuthority2], r15d; nSubAuthority2
0x18002b04c  call    cs:__imp_AllocateAndInitializeSid
0x18002b053  nop     dword ptr [rax+rax+00h]
0x18002b058  test    eax, eax
0x18002b05a  jz      loc_18002B214
0x18002b060  mov     rax, [rbp+4Fh+var_98]
0x18002b064  mov     rcx, [rbp+4Fh+var_80]; pSid
0x18002b068  mov     [rbp+4Fh+pSourceSid], rax
0x18002b06c  mov     [rbp+4Fh+var_58], rcx
0x18002b070  call    cs:__imp_GetLengthSid
0x18002b077  nop     dword ptr [rax+rax+00h]
0x18002b07c  mov     rcx, [rbp+4Fh+var_98]; pSid
0x18002b080  mov     ebx, eax
0x18002b082  call    cs:__imp_GetLengthSid
0x18002b089  nop     dword ptr [rax+rax+00h]
0x18002b08e  add     ebx, eax
0x18002b090  mov     eax, r15d
0x18002b093  test    r12, r12
0x18002b096  setnz   al
0x18002b099  lea     r14d, [rax+r13]
0x18002b09d  shl     r14d, 4
0x18002b0a1  add     r14d, 28h ; '('
0x18002b0a5  add     r14d, ebx
0x18002b0a8  add     r14d, edi
0x18002b0ab  mov     ecx, r14d; Size
0x18002b0ae  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002b0b3  mov     rsi, rax
0x18002b0b6  test    rax, rax
0x18002b0b9  jz      loc_18002B214
0x18002b0bf  lea     ecx, [rbx+rdi]
0x18002b0c2  mov     ebx, r14d
0x18002b0c5  sub     rbx, rcx
0x18002b0c8  add     rbx, rax
0x18002b0cb  mov     rax, r12
0x18002b0ce  neg     rax
0x18002b0d1  sbb     ecx, ecx
0x18002b0d3  neg     ecx
0x18002b0d5  lea     eax, [rcx+2]
0x18002b0d8  add     eax, r13d
0x18002b0db  mov     [rsi], eax
0x18002b0dd  test    r12, r12
0x18002b0e0  jnz     loc_18002B1F1
0x18002b0e6  xor     r14d, r14d
0x18002b0e9  mov     r15, rbx
0x18002b0ec  test    r13d, r13d
0x18002b0ef  jz      short loc_18002B119
0x18002b0f1  mov     r8, [rbp+4Fh+var_78]
0x18002b0f5  xor     edx, edx
0x18002b0f7  mov     rcx, rdx
0x18002b0fa  inc     r14d
0x18002b0fd  add     rcx, rcx
0x18002b100  mov     dword ptr [rsi+rcx*8+10h], 0Eh
0x18002b108  mov     rax, [r8+rdx*8]
0x18002b10c  inc     rdx
0x18002b10f  mov     [rsi+rcx*8+8], rax
0x18002b114  cmp     r14d, r13d
0x18002b117  jb      short loc_18002B0F7
0x18002b119  xor     r13d, r13d
0x18002b11c  cmp     r13d, 2
0x18002b120  jnb     short loc_18002B17D
0x18002b122  mov     ebx, r13d
0x18002b125  add     rbx, rbx
0x18002b128  mov     edi, r14d
0x18002b12b  add     rdi, rdi
0x18002b12e  mov     eax, [rbp+rbx*8+4Fh+var_60]
0x18002b132  mov     rcx, [rbp+rbx*8+4Fh+pSourceSid]; pSid
0x18002b137  mov     [rsi+rdi*8+10h], eax
0x18002b13b  mov     [rsi+rdi*8+8], r15
0x18002b140  call    cs:__imp_GetLengthSid
0x18002b147  nop     dword ptr [rax+rax+00h]
0x18002b14c  mov     r8, [rbp+rbx*8+4Fh+pSourceSid]; pSourceSid
0x18002b151  mov     ecx, eax; nDestinationSidLength
0x18002b153  mov     rdx, [rsi+rdi*8+8]; pDestinationSid
0x18002b158  mov     [rbp+4Fh+var_A0], eax
0x18002b15b  call    cs:__imp_CopySid
0x18002b162  nop     dword ptr [rax+rax+00h]
0x18002b167  test    eax, eax
0x18002b169  jz      loc_18002B214
0x18002b16f  mov     eax, [rbp+4Fh+var_A0]
0x18002b172  inc     r13d
0x18002b175  add     r15, rax
0x18002b178  inc     r14d
0x18002b17b  jmp     short loc_18002B11C
0x18002b17d  mov     rax, [rbp+4Fh+var_70]
0x18002b181  xor     r15d, r15d
0x18002b184  mov     ebx, r15d
0x18002b187  mov     [rax], rsi
0x18002b18a  mov     esi, r15d
0x18002b18d  mov     rcx, [rbp+4Fh+var_98]; pSid
0x18002b191  test    rcx, rcx
0x18002b194  jz      short loc_18002B1A2
0x18002b196  call    cs:__imp_FreeSid
0x18002b19d  nop     dword ptr [rax+rax+00h]
0x18002b1a2  mov     rcx, [rbp+4Fh+var_80]; pSid
0x18002b1a6  test    rcx, rcx
0x18002b1a9  jz      short loc_18002B1B7
0x18002b1ab  call    cs:__imp_FreeSid
0x18002b1b2  nop     dword ptr [rax+rax+00h]
0x18002b1b7  mov     rcx, rsi
0x18002b1ba  call    UBPM_MIDL_user_free
0x18002b1bf  mov     rcx, r12
0x18002b1c2  call    UBPM_MIDL_user_free
0x18002b1c7  mov     eax, ebx
0x18002b1c9  mov     rcx, [rbp+4Fh+var_38]
0x18002b1cd  xor     rcx, rsp; StackCookie
0x18002b1d0  call    __security_check_cookie
0x18002b1d5  mov     rbx, [rsp+100h+arg_18]
0x18002b1dd  add     rsp, 0D0h
0x18002b1e4  pop     r15
0x18002b1e6  pop     r14
0x18002b1e8  pop     r13
0x18002b1ea  pop     r12
0x18002b1ec  pop     rdi
0x18002b1ed  pop     rsi
0x18002b1ee  pop     rbp
0x18002b1ef  retn
0x18002b1f1  mov     r8, r12; pSourceSid
0x18002b1f4  mov     dword ptr [rsi+10h], 0Eh
0x18002b1fb  mov     rdx, rbx; pDestinationSid
0x18002b1fe  mov     [rsi+8], rbx
0x18002b202  mov     ecx, edi; nDestinationSidLength
0x18002b204  call    cs:__imp_CopySid
0x18002b20b  nop     dword ptr [rax+rax+00h]
0x18002b210  test    eax, eax
0x18002b212  jnz     short loc_18002B251
0x18002b214  call    cs:__imp_GetLastError
0x18002b21b  nop     dword ptr [rax+rax+00h]
0x18002b220  mov     ebx, eax
0x18002b222  jmp     loc_18002B18D
0x18002b227  mov     ebx, 56Dh
0x18002b22c  jmp     short loc_18002B1B7
0x18002b22e  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x18002b232  lea     r8, [rbp+4Fh+var_90]; void **
0x18002b236  call    ?UbpmUtilsGetConsumerSid@@YAKPEBGKPEAPEAXPEAK@Z; UbpmUtilsGetConsumerSid(ushort const *,ulong,void * *,ulong *)
0x18002b23b  mov     r12, [rbp+4Fh+var_90]
0x18002b23f  mov     ebx, eax
0x18002b241  test    eax, eax
0x18002b243  jnz     loc_18002B18D
0x18002b249  mov     edi, [rbp+4Fh+var_A0]
0x18002b24c  jmp     loc_18002AFB4
0x18002b251  mov     r15d, edi
0x18002b254  mov     r14d, 1
0x18002b25a  add     r15, rbx
0x18002b25d  jmp     loc_18002B119
```
