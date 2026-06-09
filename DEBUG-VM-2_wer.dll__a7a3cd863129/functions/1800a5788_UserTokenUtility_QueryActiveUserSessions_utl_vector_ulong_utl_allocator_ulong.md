# UserTokenUtility::QueryActiveUserSessions(utl::vector<ulong,utl::allocator<ulong>> &)

- ea: `0x1800a5788`
- end: `0x1800a596c`
- name: `?QueryActiveUserSessions@UserTokenUtility@@SAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800507bc`

## callees

- `0x180007e10`
- `0x18001a2cc`
- `0x18002bed4`
- `0x180053b3c`
- `0x1800a5788`
- `0x1800a5974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5887`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800a587d`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800a587d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800a5953`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800a5953`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800a57d4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800a57d4`

## string_xrefs

- `0x1800a5936`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::QueryActiveUserSessions(__int64 *a1)
{
  int v2; // ebx
  const char *v3; // rax
  __int64 v4; // rdx
  unsigned int v5; // ecx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  unsigned int i; // ebx
  unsigned int v10; // esi
  __int64 v11; // rax
  unsigned int *v12; // rax
  unsigned int *v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  const char *v18; // [rsp+28h] [rbp-18h]
  _DWORD v19[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v21; // [rsp+78h] [rbp+38h] BYREF
  __int64 v22; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF

  v23 = 0;
  v21 = 0;
  if ( !(unsigned __int8)IsQueryUserTokenPresent() )
  {
    v2 = -2147024846;
    v3 = "System does not support multiple user sessions";
    v4 = 805;
LABEL_32:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\windows\\feedback\\core\\wercommon\\libex\\usertokenutility.cpp",
      (const char *)(unsigned int)v2,
      (int)v3,
      v18);
    goto LABEL_33;
  }
  v2 = UMgrEnumerateSessionUsers(&v21, &v23);
  if ( v2 < 0 )
  {
    v3 = "UMgrEnumerateSessionUsers failed.";
    v4 = 813;
    goto LABEL_32;
  }
  v5 = v21;
  if ( !v21 || !v23 )
  {
    v2 = -2147023888;
    v3 = "No session users available.";
    v4 = 850;
    goto LABEL_32;
  }
  v6 = (a1[2] - *a1) >> 2;
  if ( v21 > v6 )
  {
    v7 = v21;
    v8 = 7 * (v6 >> 2) + 8;
    if ( v8 >= v21 )
      v7 = v8;
    if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
      v7 = 0x1FFFFFFFFFFFFFFFLL;
    if ( v21 <= v7 )
    {
      utl::vector<unsigned long,utl::allocator<unsigned long>>::_SetCapacity(a1);
      v5 = v21;
    }
  }
  for ( i = 0; i < v5; ++i )
  {
    v19[0] = *(_DWORD *)(v23 + 16LL * i + 8);
    v10 = v19[0];
    v22 = 0;
    v11 = tlx::replace<tlx::file_handle_traits>(&v22);
    if ( (unsigned int)QueryUserToken(v10, v11) || GetLastError() != 1008 )
    {
      v12 = (unsigned int *)a1[1];
      v13 = (unsigned int *)a1[2];
      if ( v12 == v13 )
      {
        v14 = *a1;
        v15 = ((__int64)v13 - *a1) >> 2;
        v16 = 7 * (v15 >> 2) + 8;
        if ( v16 > 0x1FFFFFFFFFFFFFFFLL )
          v16 = 0x1FFFFFFFFFFFFFFFLL;
        if ( v15 >= v16 || !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_SetCapacity(a1) )
        {
          v2 = -2147024882;
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
          goto LABEL_33;
        }
        if ( (unsigned __int64)v19 - v14 < a1[1] - *a1 )
          v10 = *(_DWORD *)((char *)v19 + *a1 - v14);
        *(_DWORD *)a1[1] = v10;
      }
      else
      {
        *v12 = v10;
      }
      a1[1] += 4;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
    v5 = v21;
  }
  v2 = 0;
LABEL_33:
  if ( v23 )
    UMgrFreeSessionUsers();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800a5788  mov     [rsp-28h+arg_0], rbx
0x1800a578d  push    rbp
0x1800a578e  push    rsi
0x1800a578f  push    rdi
0x1800a5790  push    r12
0x1800a5792  push    r14
0x1800a5794  mov     rbp, rsp
0x1800a5797  sub     rsp, 40h
0x1800a579b  mov     rdi, rcx
0x1800a579e  mov     [rbp+arg_18], 0
0x1800a57a6  mov     [rbp+arg_8], 0
0x1800a57ad  call    IsQueryUserTokenPresent
0x1800a57b2  test    al, al
0x1800a57b4  jnz     short loc_1800A57CC
0x1800a57b6  mov     ebx, 80070032h
0x1800a57bb  lea     rax, aSystemDoesNotS; "System does not support multiple user s"...
0x1800a57c2  mov     edx, 325h
0x1800a57c7  jmp     loc_1800A5932
0x1800a57cc  lea     rdx, [rbp+arg_18]
0x1800a57d0  lea     rcx, [rbp+arg_8]
0x1800a57d4  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800a57da  mov     ebx, eax
0x1800a57dc  test    eax, eax
0x1800a57de  jns     short loc_1800A57F1
0x1800a57e0  lea     rax, aUmgrenumerates_0; "UMgrEnumerateSessionUsers failed."
0x1800a57e7  mov     edx, 32Dh
0x1800a57ec  jmp     loc_1800A5932
0x1800a57f1  mov     ecx, [rbp+arg_8]
0x1800a57f4  test    ecx, ecx
0x1800a57f6  jz      loc_1800A5921
0x1800a57fc  cmp     [rbp+arg_18], 0
0x1800a5801  jz      loc_1800A5921
0x1800a5807  mov     rax, [rdi+10h]
0x1800a580b  mov     r12, 1FFFFFFFFFFFFFFFh
0x1800a5815  sub     rax, [rdi]
0x1800a5818  sar     rax, 2
0x1800a581c  cmp     rcx, rax
0x1800a581f  jbe     short loc_1800A584D
0x1800a5821  shr     rax, 2
0x1800a5825  mov     edx, ecx
0x1800a5827  imul    rax, 7
0x1800a582b  add     rax, 8
0x1800a582f  cmp     rax, rcx
0x1800a5832  cmovnb  rdx, rax
0x1800a5836  cmp     rdx, r12
0x1800a5839  cmova   rdx, r12
0x1800a583d  cmp     rcx, rdx
0x1800a5840  ja      short loc_1800A584D
0x1800a5842  mov     rcx, rdi
0x1800a5845  call    ?_SetCapacity@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::_SetCapacity(unsigned __int64)
0x1800a584a  mov     ecx, [rbp+arg_8]
0x1800a584d  xor     ebx, ebx
0x1800a584f  cmp     ebx, ecx
0x1800a5851  jnb     loc_1800A591D
0x1800a5857  mov     rax, [rbp+arg_18]
0x1800a585b  mov     ecx, ebx
0x1800a585d  add     rcx, rcx
0x1800a5860  mov     esi, [rax+rcx*8+8]
0x1800a5864  lea     rcx, [rbp+arg_10]
0x1800a5868  mov     [rbp+var_10], esi
0x1800a586b  mov     [rbp+arg_10], 0
0x1800a5873  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800a5878  mov     rdx, rax
0x1800a587b  mov     ecx, esi
0x1800a587d  call    cs:__imp_QueryUserToken
0x1800a5883  test    eax, eax
0x1800a5885  jnz     short loc_1800A5894
0x1800a5887  call    cs:__imp_GetLastError
0x1800a588d  cmp     eax, 3F0h
0x1800a5892  jz      short loc_1800A58FA
0x1800a5894  mov     rax, [rdi+8]
0x1800a5898  mov     rcx, [rdi+10h]
0x1800a589c  cmp     rax, rcx
0x1800a589f  jz      short loc_1800A58A5
0x1800a58a1  mov     [rax], esi
0x1800a58a3  jmp     short loc_1800A58F5
0x1800a58a5  mov     r14, [rdi]
0x1800a58a8  sub     rcx, r14
0x1800a58ab  sar     rcx, 2
0x1800a58af  mov     rax, rcx
0x1800a58b2  shr     rax, 2
0x1800a58b6  imul    rdx, rax, 7
0x1800a58ba  add     rdx, 8
0x1800a58be  cmp     rdx, r12
0x1800a58c1  cmova   rdx, r12
0x1800a58c5  cmp     rcx, rdx
0x1800a58c8  jnb     short loc_1800A590D
0x1800a58ca  mov     rcx, rdi
0x1800a58cd  call    ?_SetCapacity@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::_SetCapacity(unsigned __int64)
0x1800a58d2  test    al, al
0x1800a58d4  jz      short loc_1800A590D
0x1800a58d6  mov     r8, [rdi+8]
0x1800a58da  lea     rcx, [rbp+var_10]
0x1800a58de  mov     rdx, [rdi]
0x1800a58e1  mov     rax, r8
0x1800a58e4  sub     rax, rdx
0x1800a58e7  sub     rcx, r14
0x1800a58ea  cmp     rcx, rax
0x1800a58ed  jnb     short loc_1800A58F2
0x1800a58ef  mov     esi, [rcx+rdx]
0x1800a58f2  mov     [r8], esi
0x1800a58f5  add     qword ptr [rdi+8], 4
0x1800a58fa  lea     rcx, [rbp+arg_10]
0x1800a58fe  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a5903  mov     ecx, [rbp+arg_8]
0x1800a5906  inc     ebx
0x1800a5908  jmp     loc_1800A584F
0x1800a590d  lea     rcx, [rbp+arg_10]
0x1800a5911  mov     ebx, 8007000Eh
0x1800a5916  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a591b  jmp     short loc_1800A594A
0x1800a591d  xor     ebx, ebx
0x1800a591f  jmp     short loc_1800A594A
0x1800a5921  mov     ebx, 800703F0h
0x1800a5926  lea     rax, aNoSessionUsers; "No session users available."
0x1800a592d  mov     edx, 352h; void *
0x1800a5932  mov     rcx, [rbp+28h]; this
0x1800a5936  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x1800a593d  mov     r9d, ebx; char *
0x1800a5940  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800a5945  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a594a  mov     rcx, [rbp+arg_18]
0x1800a594e  test    rcx, rcx
0x1800a5951  jz      short loc_1800A5959
0x1800a5953  call    cs:__imp_UMgrFreeSessionUsers
0x1800a5959  mov     eax, ebx
0x1800a595b  mov     rbx, [rsp+40h+arg_0]
0x1800a5960  add     rsp, 40h
0x1800a5964  pop     r14
0x1800a5966  pop     r12
0x1800a5968  pop     rdi
0x1800a5969  pop     rsi
0x1800a596a  pop     rbp
0x1800a596b  retn
```
