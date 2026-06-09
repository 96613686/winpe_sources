# StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetStatusByUserAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::PackageStatus &)

- ea: `0x1800156e4`
- end: `0x18001581e`
- name: `?GetStatusByUserAndPackageFullName@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEAW4PackageStatus@34@@Z`
- size: `314`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, enum StateRepository::Cache::PackageStatus *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015824`

## callees

- `0x1800075e4`
- `0x18000a464`
- `0x180010854`
- `0x180015534`
- `0x1800156e4`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x1800157c6`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x1800157c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800157b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015801`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800157b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015801`

## string_xrefs

- `0x180015725`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x18001578b`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x1800157d4`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetStatusByUserAndPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        enum StateRepository::Cache::PackageStatus *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  int *v14; // [rsp+20h] [rbp-40h]
  int v15[4]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+40h] [rbp-20h]
  int v17; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  __int64 v19; // [rsp+98h] [rbp+38h] BYREF

  *(_DWORD *)a4 = 0;
  v19 = a2;
  if ( !a2 )
  {
    v7 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(a1, 0, &v19);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31D,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
        (const char *)(unsigned int)v7,
        (int)v14);
      return v8;
    }
    a2 = v19;
  }
  v17 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  if ( a2 )
  {
    v14 = v15;
    v10 = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(a1, a2, a3);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x329,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
        (const char *)(unsigned int)v10,
        (int)v15);
      goto LABEL_9;
    }
  }
  v12 = VerifyPackageFullName(a3);
  if ( v12 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x333,
           (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
           (const char *)v12,
           (unsigned int)v14);
LABEL_9:
    v11 = *((_QWORD *)&v16 + 1);
    *((_QWORD *)&v16 + 1) = 0;
    if ( v11 )
      SRCache_Free();
    return v8;
  }
  *(_DWORD *)a4 = 0;
  v13 = *((_QWORD *)&v16 + 1);
  *((_QWORD *)&v16 + 1) = 0;
  if ( v13 )
    SRCache_Free();
  return 0;
}

```

## disassembly

```asm
0x1800156e4  mov     [rsp-18h+arg_0], rbx
0x1800156e9  mov     [rsp-18h+arg_10], rsi
0x1800156ee  push    rbp
0x1800156ef  push    rdi
0x1800156f0  push    r14
0x1800156f2  mov     rbp, rsp
0x1800156f5  sub     rsp, 60h
0x1800156f9  mov     dword ptr [r9], 0
0x180015700  mov     rdi, r9
0x180015703  mov     [rbp+arg_18], rdx
0x180015707  mov     rsi, r8
0x18001570a  mov     r14, rcx
0x18001570d  test    rdx, rdx
0x180015710  jnz     short loc_180015744
0x180015712  lea     r8, [rbp+arg_18]; __int64 *
0x180015716  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18001571b  mov     ebx, eax
0x18001571d  test    eax, eax
0x18001571f  jns     short loc_180015740
0x180015721  mov     rcx, [rbp+18h]; this
0x180015725  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x18001572c  mov     r9d, eax; char *
0x18001572f  mov     edx, 31Dh; void *
0x180015734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015739  mov     eax, ebx
0x18001573b  jmp     loc_180015809
0x180015740  mov     rdx, [rbp+arg_18]
0x180015744  mov     [rbp+arg_8], 0
0x180015748  xorps   xmm0, xmm0
0x18001574b  mov     [rbp+var_10], 0
0x180015752  xorps   xmm1, xmm1
0x180015755  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18001575a  movdqu  [rbp+var_20], xmm1
0x18001575f  test    rdx, rdx
0x180015762  jz      short loc_1800157C3
0x180015764  lea     rax, [rbp+arg_8]
0x180015768  mov     r8, rsi
0x18001576b  mov     [rsp+60h+var_38], rax
0x180015770  mov     rcx, r14
0x180015773  lea     rax, [rbp+var_30]
0x180015777  mov     qword ptr [rsp+60h+var_40], rax; int
0x18001577c  call    ?GetByUserAndPackageFullName@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::PackageUserStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUserStatus_NoThrow &,bool &)
0x180015781  mov     ebx, eax
0x180015783  test    eax, eax
0x180015785  jns     short loc_1800157B8
0x180015787  mov     rcx, [rbp+18h]; this
0x18001578b  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180015792  mov     r9d, eax; char *
0x180015795  mov     edx, 329h; void *
0x18001579a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001579f  mov     rcx, qword ptr [rbp+var_20+8]
0x1800157a3  mov     qword ptr [rbp+var_20+8], 0
0x1800157ab  test    rcx, rcx
0x1800157ae  jz      short loc_180015739
0x1800157b0  call    cs:__imp_SRCache_Free
0x1800157b6  jmp     short loc_180015739
0x1800157b8  cmp     [rbp+arg_8], 0
0x1800157bc  jz      short loc_1800157C3
0x1800157be  mov     eax, [rbp+var_10]
0x1800157c1  jmp     short loc_1800157EE
0x1800157c3  mov     rcx, rsi; packageFullName
0x1800157c6  call    cs:__imp_VerifyPackageFullName
0x1800157cc  test    eax, eax
0x1800157ce  jz      short loc_1800157EC
0x1800157d0  mov     rcx, [rbp+18h]; this
0x1800157d4  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x1800157db  mov     r9d, eax; char *
0x1800157de  mov     edx, 333h; void *
0x1800157e3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800157e8  mov     ebx, eax
0x1800157ea  jmp     short loc_18001579F
0x1800157ec  xor     eax, eax
0x1800157ee  mov     [rdi], eax
0x1800157f0  mov     rcx, qword ptr [rbp+var_20+8]
0x1800157f4  mov     qword ptr [rbp+var_20+8], 0
0x1800157fc  test    rcx, rcx
0x1800157ff  jz      short loc_180015807
0x180015801  call    cs:__imp_SRCache_Free
0x180015807  xor     eax, eax
0x180015809  lea     r11, [rsp+60h+var_s0]
0x18001580e  mov     rbx, [r11+20h]
0x180015812  mov     rsi, [r11+30h]
0x180015816  mov     rsp, r11
0x180015819  pop     r14
0x18001581b  pop     rdi
0x18001581c  pop     rbp
0x18001581d  retn
```
