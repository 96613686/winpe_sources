# ATL::CAccessToken::EnablePrivilege(ushort const *,ATL::CTokenPrivileges *,bool *)

- ea: `0x180048a24`
- end: `0x180048ce0`
- name: `?EnablePrivilege@CAccessToken@ATL@@QEAA_NPEBGPEAVCTokenPrivileges@2@PEA_N@Z`
- size: `700`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this, const unsigned __int16 *, struct ATL::CTokenPrivileges *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180047ee8`

## callees

- `0x180002604`
- `0x1800483ac`
- `0x180048488`
- `0x1800486d0`
- `0x18004896c`
- `0x180048a24`
- `0x180049b50`
- `0x18004ad26`
- `0x18004b5e0`

## import_xrefs

- `ADVAPI32!LookupPrivilegeValueW` at `0x180048aec`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180048aec`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180048c5b`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180048c5b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048b21`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048c6e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048c81`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048c96`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048b21`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048c6e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048c81`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048c96`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180048b41`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180048c27`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180048b41`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180048c27`

## string_xrefs

- `0x180048ae3`: `SeSystemProfilePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ATL::CAccessToken::EnablePrivilege(
        HANDLE *this,
        const unsigned __int16 *a2,
        struct ATL::CTokenPrivileges *a3,
        bool *a4)
{
  struct _TOKEN_PRIVILEGES *v5; // rdi
  char v6; // si
  DWORD v7; // ebx
  unsigned __int64 v8; // rdx
  struct _TOKEN_PRIVILEGES *v9; // rax
  __int64 v10; // r11
  __int64 v11; // rcx
  unsigned int v12; // r9d
  __int64 v13; // r10
  __int64 v14; // r8
  LUID *v15; // r14
  __int64 v16; // r15
  __int64 v17; // rcx
  unsigned int v18; // eax
  struct _TOKEN_PRIVILEGES *v19; // rbx
  DWORD PrivilegeCount; // r9d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  struct _TOKEN_PRIVILEGES *PreviousState; // rax
  struct _TOKEN_PRIVILEGES *v26; // rcx
  struct _TOKEN_PRIVILEGES *v27; // rcx
  struct _TOKEN_PRIVILEGES BufferLength; // [rsp+30h] [rbp+0h] BYREF
  void **v30; // [rsp+40h] [rbp+10h] BYREF
  __int64 v31; // [rsp+48h] [rbp+18h] BYREF
  __int64 v32; // [rsp+50h] [rbp+20h]
  unsigned int v33; // [rsp+58h] [rbp+28h]
  int v34; // [rsp+5Ch] [rbp+2Ch]
  int v35; // [rsp+60h] [rbp+30h]
  int v36; // [rsp+64h] [rbp+34h]
  __int64 v37; // [rsp+68h] [rbp+38h]
  __int64 v38; // [rsp+70h] [rbp+40h]
  int v39; // [rsp+78h] [rbp+48h]
  int v40; // [rsp+7Ch] [rbp+4Ch]
  __int128 v41; // [rsp+80h] [rbp+50h]
  struct _TOKEN_PRIVILEGES *v42; // [rsp+90h] [rbp+60h]
  char v43; // [rsp+98h] [rbp+68h]
  struct _LUID Luid; // [rsp+A0h] [rbp+70h] BYREF
  int v45; // [rsp+A8h] [rbp+78h]

  memset_0(&v30, 0, 0x60u);
  v30 = &ATL::CTokenPrivileges::`vftable';
  v31 = 0;
  v32 = 0;
  v33 = 17;
  v37 = 0xFFFFFFFFLL;
  v38 = 0;
  v39 = 0;
  v40 = 10;
  v41 = 0;
  v34 = 1061158912;
  v35 = 1048576000;
  v36 = 1074790400;
  ATL::CAtlMap<_LUID,unsigned long,ATL::CElementTraits<_LUID>,ATL::CElementTraits<unsigned long>>::UpdateRehashThresholds(&v31);
  v5 = 0;
  v42 = 0;
  v6 = 1;
  v43 = 1;
  if ( LookupPrivilegeValueW(0, L"SeSystemProfilePrivilege", &Luid) )
  {
    v45 = 2;
    ATL::CAtlMap<_LUID,unsigned long,ATL::CElementTraits<_LUID>,ATL::CElementTraits<unsigned long>>::SetAt(&v31, &Luid);
    v43 = 1;
    v5 = v42;
  }
  v7 = v32;
  if ( (_DWORD)v32 )
  {
    free(v5);
    v5 = 0;
    v42 = 0;
    if ( v32 )
    {
      v9 = (struct _TOKEN_PRIVILEGES *)malloc(12 * v7 + 4);
      v5 = v9;
      v42 = v9;
      if ( !v9 )
        ATL::AtlThrowImpl(-2147024882);
      v9->PrivilegeCount = v7;
      v10 = 0;
      v11 = 0;
      v12 = v33;
      if ( v33 )
      {
        v13 = v31;
        while ( 1 )
        {
          v14 = *(_QWORD *)(v31 + 8 * v11);
          if ( v14 )
            break;
          v11 = (unsigned int)(v11 + 1);
          if ( (unsigned int)v11 >= v33 )
            goto LABEL_17;
        }
        do
        {
          v15 = (LUID *)v14;
          v16 = v14;
          if ( *(_QWORD *)(v14 + 16) )
          {
            v14 = *(_QWORD *)(v14 + 16);
          }
          else
          {
            LODWORD(v8) = *(_DWORD *)(v14 + 24) % v12;
            do
            {
              v8 = (unsigned int)(v8 + 1);
              v14 = 0;
              if ( (unsigned int)v8 >= v12 )
                break;
              v14 = *(_QWORD *)(v13 + 8 * v8);
            }
            while ( !v14 );
          }
          v17 = v10;
          v9->Privileges[v17].Luid = *v15;
          v9->Privileges[v17].Attributes = *(_DWORD *)(v16 + 8);
          v10 = (unsigned int)(v10 + 1);
        }
        while ( v14 );
      }
    }
LABEL_17:
    v18 = 12 * v7 + 4;
    BufferLength.PrivilegeCount = v18;
    v19 = 0;
    if ( v18 <= 0x400 )
    {
      if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v18, v8) )
      {
        PrivilegeCount = BufferLength.PrivilegeCount;
        v21 = BufferLength.PrivilegeCount + 15LL;
        if ( v21 <= BufferLength.PrivilegeCount )
          v21 = 0xFFFFFFFFFFFFFF0LL;
        v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
        v23 = alloca(v22);
        v24 = alloca(v22);
        PreviousState = &BufferLength;
LABEL_26:
        if ( AdjustTokenPrivileges(this[1], 0, v5, PrivilegeCount, PreviousState, &BufferLength.PrivilegeCount) )
        {
          while ( v19 )
          {
            v26 = v19;
            v19 = *(struct _TOKEN_PRIVILEGES **)&v19->PrivilegeCount;
            free(v26);
          }
        }
        else
        {
          while ( v19 )
          {
            v27 = v19;
            v19 = *(struct _TOKEN_PRIVILEGES **)&v19->PrivilegeCount;
            free(v27);
          }
          v6 = 0;
        }
        goto LABEL_34;
      }
      v18 = BufferLength.PrivilegeCount;
    }
    PreviousState = (struct _TOKEN_PRIVILEGES *)malloc(v18 + 16LL);
    if ( PreviousState )
    {
      *(_QWORD *)&PreviousState->PrivilegeCount = 0;
      v19 = PreviousState++;
    }
    PrivilegeCount = BufferLength.PrivilegeCount;
    goto LABEL_26;
  }
LABEL_34:
  v30 = &ATL::CTokenPrivileges::`vftable';
  free(v5);
  ATL::CAtlMap<_LUID,unsigned long,ATL::CElementTraits<_LUID>,ATL::CElementTraits<unsigned long>>::~CAtlMap<_LUID,unsigned long,ATL::CElementTraits<_LUID>,ATL::CElementTraits<unsigned long>>(&v31);
  return v6;
}

```

## disassembly

```asm
0x180048a24  push    rbp
0x180048a26  push    rdi
0x180048a27  push    r13
0x180048a29  push    r14
0x180048a2b  push    r15
0x180048a2d  sub     rsp, 0C0h
0x180048a34  lea     rbp, [rsp+30h]
0x180048a39  mov     [rbp+0B0h+arg_8], rbx
0x180048a40  mov     [rbp+0B0h+arg_10], rsi
0x180048a47  mov     rax, cs:__security_cookie
0x180048a4e  xor     rax, rbp
0x180048a51  mov     [rbp+0B0h+var_28], rax
0x180048a58  mov     r13, rcx
0x180048a5b  xor     edx, edx; Val
0x180048a5d  lea     r8d, [rdx+60h]; Size
0x180048a61  lea     rcx, [rbp+0B0h+var_A0]; void *
0x180048a65  call    memset_0
0x180048a6a  lea     r14, ??_7CTokenPrivileges@ATL@@6B@; const ATL::CTokenPrivileges::`vftable'
0x180048a71  mov     [rbp+0B0h+var_A0], r14
0x180048a75  mov     [rbp+0B0h+var_98], 0
0x180048a7d  mov     [rbp+0B0h+var_90], 0
0x180048a85  mov     [rbp+0B0h+var_88], 11h
0x180048a8c  mov     eax, 0FFFFFFFFh
0x180048a91  mov     [rbp+0B0h+var_78], rax
0x180048a95  mov     [rbp+0B0h+var_70], 0
0x180048a9d  mov     [rbp+0B0h+var_68], 0
0x180048aa4  mov     [rbp+0B0h+var_64], 0Ah
0x180048aab  xorps   xmm0, xmm0
0x180048aae  movdqa  [rbp+0B0h+var_60], xmm0
0x180048ab3  mov     [rbp+0B0h+var_84], 3F400000h
0x180048aba  mov     [rbp+0B0h+var_80], 3E800000h
0x180048ac1  mov     [rbp+0B0h+var_7C], 40100000h
0x180048ac8  lea     rcx, [rbp+0B0h+var_98]
0x180048acc  call    ?UpdateRehashThresholds@?$CAtlMap@U_LUID@@KV?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@AEAAXXZ; ATL::CAtlMap<_LUID,ulong,ATL::CElementTraits<_LUID>,ATL::CElementTraits<ulong>>::UpdateRehashThresholds(void)
0x180048ad1  nop
0x180048ad2  xor     edi, edi
0x180048ad4  mov     [rbp+0B0h+var_50], rdi
0x180048ad8  lea     esi, [rdi+1]
0x180048adb  mov     [rbp+0B0h+var_48], sil
0x180048adf  lea     r8, [rbp+0B0h+Luid]; lpLuid
0x180048ae3  lea     rdx, aSesystemprofil; "SeSystemProfilePrivilege"
0x180048aea  xor     ecx, ecx; lpSystemName
0x180048aec  call    cs:__imp_LookupPrivilegeValueW
0x180048af2  test    eax, eax
0x180048af4  jz      short loc_180048B13
0x180048af6  lea     r8d, [rdi+2]
0x180048afa  mov     [rbp+0B0h+var_38], r8d
0x180048afe  lea     rdx, [rbp+0B0h+Luid]
0x180048b02  lea     rcx, [rbp+0B0h+var_98]
0x180048b06  call    ?SetAt@?$CAtlMap@U_LUID@@KV?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAPEAU__POSITION@@AEBU_LUID@@K@Z; ATL::CAtlMap<_LUID,ulong,ATL::CElementTraits<_LUID>,ATL::CElementTraits<ulong>>::SetAt(_LUID const &,ulong)
0x180048b0b  mov     [rbp+0B0h+var_48], sil
0x180048b0f  mov     rdi, [rbp+0B0h+var_50]
0x180048b13  mov     ebx, dword ptr [rbp+0B0h+var_90]
0x180048b16  test    ebx, ebx
0x180048b18  jz      loc_180048C8F
0x180048b1e  mov     rcx, rdi; Block
0x180048b21  call    cs:__imp_free
0x180048b27  xor     edi, edi
0x180048b29  mov     [rbp+0B0h+var_50], rdi
0x180048b2d  cmp     [rbp+0B0h+var_90], rdi
0x180048b31  jz      loc_180048BD0
0x180048b37  lea     eax, [rbx+rbx*2]
0x180048b3a  lea     ecx, ds:4[rax*4]; Size
0x180048b41  call    cs:__imp_malloc
0x180048b47  mov     rdi, rax
0x180048b4a  mov     [rbp+0B0h+var_50], rax
0x180048b4e  test    rax, rax
0x180048b51  jz      loc_180048CD5
0x180048b57  mov     [rax], ebx
0x180048b59  xor     r11d, r11d
0x180048b5c  xor     ecx, ecx
0x180048b5e  mov     r9d, [rbp+0B0h+var_88]
0x180048b62  test    r9d, r9d
0x180048b65  jz      short loc_180048BD0
0x180048b67  mov     r10, [rbp+0B0h+var_98]
0x180048b6b  mov     r8, [r10+rcx*8]
0x180048b6f  test    r8, r8
0x180048b72  jnz     short loc_180048B7D
0x180048b74  add     ecx, esi
0x180048b76  cmp     ecx, r9d
0x180048b79  jb      short loc_180048B6B
0x180048b7b  jmp     short loc_180048BD0
0x180048b7d  mov     r14, r8
0x180048b80  mov     r15, r8
0x180048b83  mov     rax, [r8+10h]
0x180048b87  test    rax, rax
0x180048b8a  jz      short loc_180048B91
0x180048b8c  mov     r8, rax
0x180048b8f  jmp     short loc_180048BAD
0x180048b91  xor     edx, edx
0x180048b93  mov     eax, [r8+18h]
0x180048b97  div     r9d
0x180048b9a  add     edx, esi; unsigned __int64
0x180048b9c  xor     r8d, r8d
0x180048b9f  cmp     edx, r9d
0x180048ba2  jnb     short loc_180048BAD
0x180048ba4  mov     r8, [r10+rdx*8]
0x180048ba8  test    r8, r8
0x180048bab  jz      short loc_180048B9A
0x180048bad  lea     rcx, [r11+r11*2]
0x180048bb1  mov     rax, [r14]
0x180048bb4  mov     [rdi+rcx*4+4], rax
0x180048bb9  mov     eax, [r15+8]
0x180048bbd  mov     [rdi+rcx*4+0Ch], eax
0x180048bc1  add     r11d, esi
0x180048bc4  test    r8, r8
0x180048bc7  jnz     short loc_180048B7D
0x180048bc9  lea     r14, ??_7CTokenPrivileges@ATL@@6B@; const ATL::CTokenPrivileges::`vftable'
0x180048bd0  lea     eax, [rbx+rbx*2]
0x180048bd3  lea     eax, ds:4[rax*4]
0x180048bda  mov     [rbp+0B0h+BufferLength.PrivilegeCount], eax
0x180048bdd  xor     ebx, ebx
0x180048bdf  cmp     eax, 400h
0x180048be4  ja      short loc_180048C21
0x180048be6  mov     ecx, eax; this
0x180048be8  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180048bed  test    al, al
0x180048bef  jz      short loc_180048C1E
0x180048bf1  mov     r9d, [rbp+0B0h+BufferLength.PrivilegeCount]
0x180048bf5  lea     rcx, [r9+0Fh]
0x180048bf9  cmp     rcx, r9
0x180048bfc  ja      short loc_180048C08
0x180048bfe  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180048c08  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180048c0c  mov     rax, rcx
0x180048c0f  call    _alloca_probe
0x180048c14  sub     rsp, rcx
0x180048c17  lea     rax, [rsp+0E0h+BufferLength]
0x180048c1c  jmp     short loc_180048C44
0x180048c1e  mov     eax, [rbp+0B0h+BufferLength.PrivilegeCount]
0x180048c21  mov     ecx, eax
0x180048c23  add     rcx, 10h; Size
0x180048c27  call    cs:__imp_malloc
0x180048c2d  test    rax, rax
0x180048c30  jz      short loc_180048C40
0x180048c32  mov     qword ptr [rax], 0
0x180048c39  mov     rbx, rax
0x180048c3c  add     rax, 10h
0x180048c40  mov     r9d, [rbp+0B0h+BufferLength.PrivilegeCount]; BufferLength
0x180048c44  lea     rcx, [rbp+0B0h+BufferLength]
0x180048c48  mov     [rsp+0E0h+ReturnLength], rcx; ReturnLength
0x180048c4d  mov     [rsp+0E0h+PreviousState], rax; PreviousState
0x180048c52  mov     r8, rdi; NewState
0x180048c55  xor     edx, edx; DisableAllPrivileges
0x180048c57  mov     rcx, [r13+8]; TokenHandle
0x180048c5b  call    cs:__imp_AdjustTokenPrivileges
0x180048c61  nop
0x180048c62  test    eax, eax
0x180048c64  jz      short loc_180048C87
0x180048c66  jmp     short loc_180048C74
0x180048c68  mov     rcx, rbx; Block
0x180048c6b  mov     rbx, [rbx]
0x180048c6e  call    cs:__imp_free
0x180048c74  test    rbx, rbx
0x180048c77  jnz     short loc_180048C68
0x180048c79  jmp     short loc_180048C8F
0x180048c7b  mov     rcx, rbx; Block
0x180048c7e  mov     rbx, [rbx]
0x180048c81  call    cs:__imp_free
0x180048c87  test    rbx, rbx
0x180048c8a  jnz     short loc_180048C7B
0x180048c8c  xor     sil, sil
0x180048c8f  mov     [rbp+0B0h+var_A0], r14
0x180048c93  mov     rcx, rdi; Block
0x180048c96  call    cs:__imp_free
0x180048c9c  lea     rcx, [rbp+0B0h+var_98]
0x180048ca0  call    ??1?$CAtlMap@U_LUID@@KV?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAA@XZ; ATL::CAtlMap<_LUID,ulong,ATL::CElementTraits<_LUID>,ATL::CElementTraits<ulong>>::~CAtlMap<_LUID,ulong,ATL::CElementTraits<_LUID>,ATL::CElementTraits<ulong>>(void)
0x180048ca5  mov     al, sil
0x180048ca8  mov     rcx, [rbp+0B0h+var_28]
0x180048caf  xor     rcx, rbp; StackCookie
0x180048cb2  call    __security_check_cookie
0x180048cb7  mov     rbx, [rbp+0B0h+arg_8]
0x180048cbe  mov     rsi, [rbp+0B0h+arg_10]
0x180048cc5  lea     rsp, [rbp+90h]
0x180048ccc  pop     r15
0x180048cce  pop     r14
0x180048cd0  pop     r13
0x180048cd2  pop     rdi
0x180048cd3  pop     rbp
0x180048cd4  retn
0x180048cd5  mov     ecx, 8007000Eh; int
0x180048cda  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
