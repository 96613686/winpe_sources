# GetRoamingProfileDir

- ea: `0x1400640a4`
- end: `0x1400645e4`
- name: `GetRoamingProfileDir`
- size: `1344`
- prototype: `__int64 __fastcall(HANDLE Token, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400645ec`

## callees

- `0x140004280`
- `0x140006061`
- `0x140006304`
- `0x140007404`
- `0x140018bec`
- `0x140020c60`
- `0x14003e4dc`
- `0x14006393c`
- `0x1400639cc`
- `0x1400640a4`
- `0x1400659e4`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x140064361`
- `ADVAPI32!SetThreadToken` at `0x140064361`
- `KERNEL32!GetLastError` at `0x1400643a6`
- `KERNEL32!GetLastError` at `0x1400643a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140064324`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140064324`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400641b5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14006437d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140064483`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400641b5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14006437d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140064483`
- `NETAPI32!NetApiBufferFree` at `0x1400642b5`
- `NETAPI32!NetApiBufferFree` at `0x1400642c7`
- `NETAPI32!NetApiBufferFree` at `0x140064471`
- `NETAPI32!NetApiBufferFree` at `0x14006455f`
- `NETAPI32!NetApiBufferFree` at `0x1400642b5`
- `NETAPI32!NetApiBufferFree` at `0x1400642c7`
- `NETAPI32!NetApiBufferFree` at `0x140064471`
- `NETAPI32!NetApiBufferFree` at `0x14006455f`
- `NETAPI32!NetUserGetInfo` at `0x140064457`
- `NETAPI32!NetUserGetInfo` at `0x140064457`
- `NETAPI32!DsGetDcNameW` at `0x14006424d`
- `NETAPI32!DsGetDcNameW` at `0x14006424d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall GetRoamingProfileDir(HANDLE Token, _QWORD *a2)
{
  char *v2; // r14
  unsigned __int64 *v4; // r12
  _WORD *v5; // rcx
  int v6; // ecx
  __int64 NameAndFQDNDomain; // rbx
  unsigned int v9; // eax
  __int64 v10; // rdi
  char *v11; // rax
  const char *v12; // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // r8
  LPWSTR DomainControllerName; // r9
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rdx
  LPCWSTR *v18; // rdi
  __int64 v19; // rbx
  __int128 *v20; // rdx
  LPCWSTR *v21; // rcx
  BOOL v22; // eax
  char *v23; // rax
  const char *v24; // rax
  unsigned __int64 FileId; // rbx
  __int64 v26; // rdi
  const WCHAR *v27; // rdx
  const WCHAR *v28; // rcx
  DWORD Info; // eax
  __int64 v30; // r8
  __int64 v31; // rdi
  char *v32; // rax
  const char *v33; // rax
  unsigned __int64 v34; // rbx
  _WORD *v35; // r9
  LPBYTE bufptr; // [rsp+30h] [rbp-E8h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+38h] [rbp-E0h] BYREF
  BOOL v38; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v39[24]; // [rsp+48h] [rbp-D0h] BYREF
  LPCWSTR DomainName[2]; // [rsp+60h] [rbp-B8h] BYREF
  unsigned __int64 v41; // [rsp+70h] [rbp-A8h]
  unsigned __int64 v42; // [rsp+78h] [rbp-A0h]
  LPCWSTR servername[2]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v44; // [rsp+90h] [rbp-88h]
  unsigned __int64 v45; // [rsp+98h] [rbp-80h]
  LPCWSTR username[2]; // [rsp+A0h] [rbp-78h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-68h]
  __int128 v48; // [rsp+C0h] [rbp-58h] BYREF
  __m128i v49; // [rsp+D0h] [rbp-48h]

  v2 = (char *)a2;
  v4 = a2 + 2;
  a2[2] = 0;
  if ( a2[3] <= 7u )
    v5 = a2;
  else
    v5 = (_WORD *)*a2;
  *v5 = 0;
  *(_OWORD *)DomainName = 0;
  v41 = 0;
  v42 = 7;
  LOWORD(DomainName[0]) = 0;
  *(_OWORD *)username = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(username[0]) = 0;
  NameAndFQDNDomain = GetNameAndFQDNDomain(Token);
  if ( (NameAndFQDNDomain & 0x8000000000LL) != 0 )
  {
    v48 = 0;
    v49 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v48) = 0;
    v9 = SWGetComputerName(v6, (__int64)&v48);
    v10 = v9;
    if ( v9 )
    {
      v11 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
      if ( v11 )
        v12 = v11 + 1;
      else
        v12 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
      v13 = v10
          | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12) << 52)
          | 0x262500000000LL;
      std::wstring::~wstring((char **)&v48);
      std::wstring::~wstring((char **)username);
      std::wstring::~wstring((char **)DomainName);
      return v13;
    }
    else
    {
      DomainControllerInfo = 0;
      if ( DsGetDcNameW(0, (LPCWSTR)DomainName, 0, 0, 0, &DomainControllerInfo) )
      {
        if ( DomainControllerInfo )
          NetApiBufferFree(DomainControllerInfo);
        v16 = -1;
      }
      else
      {
        DomainControllerName = DomainControllerInfo->DomainControllerName;
        v16 = -1;
        v17 = -1;
        do
          ++v17;
        while ( DomainControllerName[v17] );
        if ( v17 > v42 )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)DomainName,
            v17,
            v14,
            DomainControllerName);
        }
        else
        {
          v18 = DomainName;
          if ( v42 > 7 )
            v18 = (LPCWSTR *)DomainName[0];
          v41 = v17;
          v19 = 2 * v17;
          memmove_0(v18, DomainControllerName, 2 * v17);
          *(_WORD *)((char *)v18 + v19) = 0;
        }
        NetApiBufferFree(DomainControllerInfo);
      }
      *(_OWORD *)servername = 0;
      v44 = 0;
      v45 = 7;
      LOWORD(servername[0]) = 0;
      v20 = &v48;
      if ( v49.m128i_i64[1] > 7uLL )
        v20 = (__int128 *)v48;
      v21 = DomainName;
      if ( v42 > 7 )
        v21 = (LPCWSTR *)DomainName[0];
      if ( (unsigned int)_o__wcsicmp(v21, v20) )
        std::wstring::operator=(servername, DomainName);
      bufptr = 0;
      v38 = 0;
      softgrid::shared::revert_to_self::revert_to_self((softgrid::shared::revert_to_self *)v39);
      v22 = v38;
      if ( !v38 )
      {
        v22 = SetThreadToken(0, Token);
        v38 = v22;
      }
      if ( v22 )
      {
        v27 = (const WCHAR *)username;
        if ( si128.m128i_i64[1] > 7uLL )
          v27 = username[0];
        if ( v44 )
        {
          v28 = (const WCHAR *)servername;
          if ( v45 > 7 )
            v28 = servername[0];
        }
        else
        {
          v28 = 0;
        }
        Info = NetUserGetInfo(v28, v27, 4u, &bufptr);
        v31 = Info;
        if ( Info )
        {
          if ( bufptr )
            NetApiBufferFree(bufptr);
          v32 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
          if ( v32 )
            v33 = v32 + 1;
          else
            v33 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
          v34 = v31
              | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v33) << 52)
              | 0x2B2500000000LL;
          softgrid::shared::impersonate_user::~impersonate_user((softgrid::shared::impersonate_user *)&v38);
          std::wstring::~wstring((char **)servername);
          std::wstring::~wstring((char **)&v48);
          std::wstring::~wstring((char **)username);
          std::wstring::~wstring((char **)DomainName);
          return v34;
        }
        else
        {
          v35 = (_WORD *)*((_QWORD *)bufptr + 21);
          if ( v35 )
          {
            do
              ++v16;
            while ( v35[v16] );
            if ( v16 > *((_QWORD *)v2 + 3) )
            {
              std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
                (char **)v2,
                v16,
                v30,
                v35);
            }
            else
            {
              if ( *((_QWORD *)v2 + 3) > 7u )
                v2 = *(char **)v2;
              *v4 = v16;
              memmove_0(v2, v35, 2 * v16);
              *(_WORD *)&v2[2 * v16] = 0;
            }
          }
          NetApiBufferFree(bufptr);
          softgrid::shared::impersonate_user::~impersonate_user((softgrid::shared::impersonate_user *)&v38);
          std::wstring::~wstring((char **)servername);
          std::wstring::~wstring((char **)&v48);
          std::wstring::~wstring((char **)username);
          std::wstring::~wstring((char **)DomainName);
          return 0x8000000000LL;
        }
      }
      else
      {
        v23 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
        if ( v23 )
          v24 = v23 + 1;
        else
          v24 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v24);
        v26 = (FileId << 52) | GetLastError() | 0x2A2500000000LL;
        softgrid::shared::impersonate_user::~impersonate_user((softgrid::shared::impersonate_user *)&v38);
        std::wstring::~wstring((char **)servername);
        std::wstring::~wstring((char **)&v48);
        std::wstring::~wstring((char **)username);
        std::wstring::~wstring((char **)DomainName);
        return v26;
      }
    }
  }
  else
  {
    std::wstring::~wstring((char **)username);
    std::wstring::~wstring((char **)DomainName);
    return NameAndFQDNDomain;
  }
}

```

## disassembly

```asm
0x1400640a4  mov     [rsp+arg_10], rbx
0x1400640a9  mov     [rsp+arg_18], rsi
0x1400640ae  push    rdi
0x1400640af  push    r12
0x1400640b1  push    r13
0x1400640b3  push    r14
0x1400640b5  push    r15
0x1400640b7  sub     rsp, 0F0h
0x1400640be  mov     rax, cs:__security_cookie
0x1400640c5  xor     rax, rsp
0x1400640c8  mov     [rsp+118h+var_38], rax
0x1400640d0  mov     r14, rdx
0x1400640d3  mov     r15, rcx
0x1400640d6  lea     r12, [rdx+10h]
0x1400640da  xor     r13d, r13d
0x1400640dd  mov     [r12], r13
0x1400640e1  cmp     qword ptr [rdx+18h], 7
0x1400640e6  jbe     short loc_1400640ED
0x1400640e8  mov     rcx, [rdx]
0x1400640eb  jmp     short loc_1400640F0
0x1400640ed  mov     rcx, r14
0x1400640f0  mov     [rcx], r13w
0x1400640f4  xorps   xmm0, xmm0
0x1400640f7  movups  xmmword ptr [rsp+118h+DomainName], xmm0
0x1400640fc  mov     [rsp+118h+var_A8], r13
0x140064101  mov     [rsp+118h+var_A0], 7
0x14006410a  mov     word ptr [rsp+118h+DomainName], r13w
0x140064110  movups  xmmword ptr [rsp+118h+username], xmm0
0x140064118  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140064120  movdqu  [rsp+118h+var_68], xmm1
0x140064129  mov     word ptr [rsp+118h+username], r13w
0x140064132  lea     r8, [rsp+118h+DomainName]
0x140064137  lea     rdx, [rsp+118h+username]
0x14006413f  mov     rcx, r15; Token
0x140064142  call    GetNameAndFQDNDomain
0x140064147  mov     rbx, rax
0x14006414a  bt      rax, 27h ; '''
0x14006414f  jb      short loc_140064171
0x140064151  lea     rcx, [rsp+118h+username]
0x140064159  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006415e  nop
0x14006415f  lea     rcx, [rsp+118h+DomainName]
0x140064164  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140064169  mov     rax, rbx
0x14006416c  jmp     loc_1400645B6
0x140064171  xorps   xmm0, xmm0
0x140064174  movups  [rsp+118h+var_58], xmm0
0x14006417c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140064184  movdqu  [rsp+118h+var_48], xmm1
0x14006418d  mov     word ptr [rsp+118h+var_58], r13w
0x140064196  lea     rdx, [rsp+118h+var_58]
0x14006419e  call    ?SWGetComputerName@@YAKW4_COMPUTER_NAME_FORMAT@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; SWGetComputerName(_COMPUTER_NAME_FORMAT,std::wstring &)
0x1400641a3  mov     edi, eax
0x1400641a5  test    eax, eax
0x1400641a7  jz      short loc_140064220
0x1400641a9  mov     edx, 5Ch ; '\'; Ch
0x1400641ae  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x1400641b5  call    cs:__imp_strrchr
0x1400641bb  test    rax, rax
0x1400641be  jz      short loc_1400641C5
0x1400641c0  inc     rax
0x1400641c3  jmp     short loc_1400641CC
0x1400641c5  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x1400641cc  mov     rdx, rax; char *
0x1400641cf  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400641d6  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400641db  mov     rbx, rax
0x1400641de  shl     rbx, 34h
0x1400641e2  or      rbx, rdi
0x1400641e5  mov     rax, 262500000000h
0x1400641ef  or      rbx, rax
0x1400641f2  lea     rcx, [rsp+118h+var_58]
0x1400641fa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400641ff  nop
0x140064200  lea     rcx, [rsp+118h+username]
0x140064208  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006420d  nop
0x14006420e  lea     rcx, [rsp+118h+DomainName]
0x140064213  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140064218  mov     rax, rbx
0x14006421b  jmp     loc_1400645B6
0x140064220  mov     [rsp+118h+var_E0], r13
0x140064225  lea     rdx, [rsp+118h+DomainName]
0x14006422a  cmp     [rsp+118h+var_A0], 7
0x140064230  cmova   rdx, [rsp+118h+DomainName]; DomainName
0x140064236  lea     rax, [rsp+118h+var_E0]
0x14006423b  mov     [rsp+118h+DomainControllerInfo], rax; DomainControllerInfo
0x140064240  mov     [rsp+118h+Flags], r13d; Flags
0x140064245  xor     r9d, r9d; SiteName
0x140064248  xor     r8d, r8d; DomainGuid
0x14006424b  xor     ecx, ecx; ComputerName
0x14006424d  call    cs:__imp_DsGetDcNameW
0x140064253  test    eax, eax
0x140064255  jnz     short loc_1400642BD
0x140064257  mov     rax, [rsp+118h+var_E0]
0x14006425c  mov     r9, [rax]
0x14006425f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140064263  mov     rdx, rsi
0x140064266  inc     rdx
0x140064269  cmp     [r9+rdx*2], r13w
0x14006426e  jnz     short loc_140064266
0x140064270  cmp     rdx, [rsp+118h+var_A0]
0x140064275  ja      short loc_1400642A6
0x140064277  lea     rdi, [rsp+118h+DomainName]
0x14006427c  cmp     [rsp+118h+var_A0], 7
0x140064282  cmova   rdi, [rsp+118h+DomainName]
0x140064288  mov     [rsp+118h+var_A8], rdx
0x14006428d  lea     rbx, [rdx+rdx]
0x140064291  mov     r8, rbx; Size
0x140064294  mov     rdx, r9; Src
0x140064297  mov     rcx, rdi; void *
0x14006429a  call    memmove_0
0x14006429f  mov     [rbx+rdi], r13w
0x1400642a4  jmp     short loc_1400642B0
0x1400642a6  lea     rcx, [rsp+118h+DomainName]
0x1400642ab  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x1400642b0  mov     rcx, [rsp+118h+var_E0]; Buffer
0x1400642b5  call    cs:__imp_NetApiBufferFree
0x1400642bb  jmp     short loc_1400642D1
0x1400642bd  mov     rcx, [rsp+118h+var_E0]; Buffer
0x1400642c2  test    rcx, rcx
0x1400642c5  jz      short loc_1400642CD
0x1400642c7  call    cs:__imp_NetApiBufferFree
0x1400642cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400642d1  xorps   xmm0, xmm0
0x1400642d4  movups  xmmword ptr [rsp+118h+servername], xmm0
0x1400642dc  mov     [rsp+118h+var_88], r13
0x1400642e4  mov     [rsp+118h+var_80], 7
0x1400642f0  mov     word ptr [rsp+118h+servername], r13w
0x1400642f9  lea     rdx, [rsp+118h+var_58]
0x140064301  cmp     qword ptr [rsp+118h+var_48+8], 7
0x14006430a  cmova   rdx, qword ptr [rsp+118h+var_58]
0x140064313  lea     rcx, [rsp+118h+DomainName]
0x140064318  cmp     [rsp+118h+var_A0], 7
0x14006431e  cmova   rcx, [rsp+118h+DomainName]
0x140064324  call    cs:__imp__o__wcsicmp
0x14006432a  test    eax, eax
0x14006432c  jz      short loc_140064340
0x14006432e  lea     rdx, [rsp+118h+DomainName]
0x140064333  lea     rcx, [rsp+118h+servername]
0x14006433b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140064340  mov     [rsp+118h+bufptr], r13
0x140064345  mov     [rsp+118h+var_D8], r13d
0x14006434a  lea     rcx, [rsp+118h+var_D0]; this
0x14006434f  call    ??0revert_to_self@shared@softgrid@@QEAA@XZ; softgrid::shared::revert_to_self::revert_to_self(void)
0x140064354  mov     eax, [rsp+118h+var_D8]
0x140064358  test    eax, eax
0x14006435a  jnz     short loc_14006436B
0x14006435c  mov     rdx, r15; Token
0x14006435f  xor     ecx, ecx; Thread
0x140064361  call    cs:__imp_SetThreadToken
0x140064367  mov     [rsp+118h+var_D8], eax
0x14006436b  test    eax, eax
0x14006436d  jnz     loc_140064409
0x140064373  lea     edx, [rax+5Ch]; Ch
0x140064376  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x14006437d  call    cs:__imp_strrchr
0x140064383  test    rax, rax
0x140064386  jz      short loc_14006438D
0x140064388  inc     rax
0x14006438b  jmp     short loc_140064394
0x14006438d  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140064394  mov     rdx, rax; char *
0x140064397  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14006439e  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400643a3  mov     rbx, rax
0x1400643a6  call    cs:__imp_GetLastError
0x1400643ac  mov     edi, eax
0x1400643ae  shl     rbx, 34h
0x1400643b2  or      rdi, rbx
0x1400643b5  mov     rax, 2A2500000000h
0x1400643bf  or      rdi, rax
0x1400643c2  lea     rcx, [rsp+118h+var_D8]; this
0x1400643c7  call    ??1impersonate_user@shared@softgrid@@QEAA@XZ; softgrid::shared::impersonate_user::~impersonate_user(void)
0x1400643cc  nop
0x1400643cd  lea     rcx, [rsp+118h+servername]
0x1400643d5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400643da  nop
0x1400643db  lea     rcx, [rsp+118h+var_58]
0x1400643e3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400643e8  nop
0x1400643e9  lea     rcx, [rsp+118h+username]
0x1400643f1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400643f6  nop
0x1400643f7  lea     rcx, [rsp+118h+DomainName]
0x1400643fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140064401  mov     rax, rdi
0x140064404  jmp     loc_1400645B6
0x140064409  lea     rdx, [rsp+118h+username]
0x140064411  cmp     qword ptr [rsp+118h+var_68+8], 7
0x14006441a  cmova   rdx, [rsp+118h+username]; username
0x140064423  cmp     [rsp+118h+var_88], r13
0x14006442b  jnz     short loc_140064432
0x14006442d  mov     rcx, r13
0x140064430  jmp     short loc_14006444C
0x140064432  lea     rcx, [rsp+118h+servername]
0x14006443a  cmp     [rsp+118h+var_80], 7
0x140064443  cmova   rcx, [rsp+118h+servername]; servername
0x14006444c  lea     r9, [rsp+118h+bufptr]; bufptr
0x140064451  mov     r8d, 4; level
0x140064457  call    cs:__imp_NetUserGetInfo
0x14006445d  mov     edi, eax
0x14006445f  test    eax, eax
0x140064461  jz      loc_140064507
0x140064467  mov     rcx, [rsp+118h+bufptr]; Buffer
0x14006446c  test    rcx, rcx
0x14006446f  jz      short loc_140064477
0x140064471  call    cs:__imp_NetApiBufferFree
0x140064477  mov     edx, 5Ch ; '\'; Ch
0x14006447c  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140064483  call    cs:__imp_strrchr
0x140064489  test    rax, rax
0x14006448c  jz      short loc_140064493
0x14006448e  inc     rax
0x140064491  jmp     short loc_14006449A
0x140064493  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x14006449a  mov     rdx, rax; char *
0x14006449d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400644a4  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400644a9  mov     rbx, rax
0x1400644ac  shl     rbx, 34h
0x1400644b0  or      rbx, rdi
0x1400644b3  mov     rax, 2B2500000000h
0x1400644bd  or      rbx, rax
0x1400644c0  lea     rcx, [rsp+118h+var_D8]; this
0x1400644c5  call    ??1impersonate_user@shared@softgrid@@QEAA@XZ; softgrid::shared::impersonate_user::~impersonate_user(void)
0x1400644ca  nop
0x1400644cb  lea     rcx, [rsp+118h+servername]
0x1400644d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400644d8  nop
0x1400644d9  lea     rcx, [rsp+118h+var_58]
0x1400644e1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400644e6  nop
0x1400644e7  lea     rcx, [rsp+118h+username]
0x1400644ef  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400644f4  nop
0x1400644f5  lea     rcx, [rsp+118h+DomainName]
0x1400644fa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400644ff  mov     rax, rbx
0x140064502  jmp     loc_1400645B6
0x140064507  mov     rax, [rsp+118h+bufptr]
0x14006450c  mov     r9, [rax+0A8h]
0x140064513  test    r9, r9
0x140064516  jz      short loc_14006455A
0x140064518  inc     rsi
0x14006451b  cmp     [r9+rsi*2], r13w
0x140064520  jnz     short loc_140064518
0x140064522  cmp     rsi, [r14+18h]
0x140064526  ja      short loc_14006454F
0x140064528  cmp     qword ptr [r14+18h], 7
0x14006452d  jbe     short loc_140064532
0x14006452f  mov     r14, [r14]
0x140064532  mov     [r12], rsi
0x140064536  lea     rbx, [rsi+rsi]
0x14006453a  mov     r8, rbx; Size
0x14006453d  mov     rdx, r9; Src
0x140064540  mov     rcx, r14; void *
0x140064543  call    memmove_0
0x140064548  mov     [rbx+r14], r13w
0x14006454d  jmp     short loc_14006455A
0x14006454f  mov     rdx, rsi
0x140064552  mov     rcx, r14
0x140064555  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14006455a  mov     rcx, [rsp+118h+bufptr]; Buffer
0x14006455f  call    cs:__imp_NetApiBufferFree
0x140064565  nop
0x140064566  lea     rcx, [rsp+118h+var_D8]; this
0x14006456b  call    ??1impersonate_user@shared@softgrid@@QEAA@XZ; softgrid::shared::impersonate_user::~impersonate_user(void)
0x140064570  nop
0x140064571  lea     rcx, [rsp+118h+servername]
0x140064579  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006457e  nop
0x14006457f  lea     rcx, [rsp+118h+var_58]
0x140064587  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006458c  nop
0x14006458d  lea     rcx, [rsp+118h+username]
0x140064595  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006459a  nop
0x14006459b  lea     rcx, [rsp+118h+DomainName]
0x1400645a0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400645a5  mov     rax, 8000000000h
0x1400645af  jmp     short loc_1400645B6
0x1400645b1  mov     rax, [rsp+118h+bufptr]
0x1400645b6  mov     rcx, [rsp+118h+var_38]
0x1400645be  xor     rcx, rsp; StackCookie
0x1400645c1  call    __security_check_cookie
0x1400645c6  lea     r11, [rsp+118h+var_28]
0x1400645ce  mov     rbx, [r11+40h]
0x1400645d2  mov     rsi, [r11+48h]
0x1400645d6  mov     rsp, r11
0x1400645d9  pop     r15
0x1400645db  pop     r14
0x1400645dd  pop     r13
0x1400645df  pop     r12
0x1400645e1  pop     rdi
0x1400645e2  retn
```
