# CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)

- ea: `0x140012720`
- end: `0x1400129f2`
- name: `?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, struct CHString *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012b80`
- `0x140012e50`
- `0x1400133e0`

## callees

- `0x1400027e1`
- `0x14000298c`
- `0x140005810`
- `0x140010190`
- `0x140010540`
- `0x140010bc0`
- `0x1400111d0`
- `0x140011280`
- `0x140012720`
- `0x140012bc0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012802`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012847`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400128e8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14001293a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400129d2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012802`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012847`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400128e8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14001293a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400129d2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400127a7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012902`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400127a7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012902`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012775`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012775`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct CHString *a4)
{
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rbx
  DWORD v10; // r14d
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int16 *v13; // r15
  __int64 v14; // rdi
  DWORD i; // r12d
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rdi
  DWORD v19; // edi
  int v20; // r14d
  unsigned __int16 *Buffer; // rax
  __int64 v22; // rax
  DWORD cbData; // [rsp+30h] [rbp-58h] BYREF
  DWORD Type; // [rsp+34h] [rbp-54h] BYREF
  int pExceptionObject; // [rsp+38h] [rbp-50h] BYREF
  int v26; // [rsp+3Ch] [rbp-4Ch] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-48h]
  unsigned __int16 *v28; // [rsp+48h] [rbp-40h]

  cbData = 0;
  Type = 0;
  CHString::operator=(a4, (unsigned __int16 *)&qword_14001BC40);
  if ( !RegQueryValueExW(a2, a3, 0, &Type, 0, &cbData) )
  {
    v8 = cbData;
    if ( cbData )
    {
      if ( Type - 1 <= 1 || Type == 7 )
      {
        v8 = cbData + 2;
        cbData += 2;
      }
      v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v8);
      v27 = v9;
      v10 = cbData;
      if ( !v9 )
      {
        pExceptionObject = 0;
        throw (CHeap_Exception *)&pExceptionObject;
      }
      if ( !((unsigned int (__stdcall *)(CRegistry *, HKEY, const unsigned __int16 *, void *, unsigned int *, unsigned int *))CRegistry::GetCurrentRawKeyValue)(
              this,
              a2,
              a3,
              v9,
              &Type,
              &cbData) )
      {
        switch ( Type )
        {
          case 1u:
          case 2u:
            if ( cbData >= v10 )
              v22 = v10 - 1;
            else
              v22 = cbData;
            *((_BYTE *)v9 + v22) = 0;
            CHString::operator=(a4, v9);
            goto LABEL_36;
          case 3u:
            CHString::Empty(a4);
            v19 = cbData & 1;
            v20 = (cbData >> 1) + v19;
            Buffer = CHString::GetBuffer((const unsigned __int16 **)a4, v20);
            memcpy_0(Buffer, v9, cbData);
            if ( v19 )
              *(_BYTE *)(cbData + *(_QWORD *)a4) = 0;
            CHString::GetBufferSetLength(a4, v20);
            goto LABEL_36;
          case 4u:
            if ( cbData == 4 )
            {
              v17 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x200u);
              v18 = v17;
              v28 = v17;
              if ( !v17 )
              {
                v26 = 0;
                throw (CHeap_Exception *)&v26;
              }
              if ( __eh34_try(0, 1) )
              {
                __eh34_scope_strut(1);
                StringCchPrintfW(v17, 0x100u, L"%ld", *(unsigned int *)v9);
                CHString::operator=(a4, v18);
                CWin32DefaultArena::WbemMemFree(v18);
                v28 = 0;
              }
              if ( __eh34_catch(1) )
              {
                if ( __eh34_catch_type(1, &CHeap_Exception `RTTI Type Descriptor', 0) )
                {
                  CWin32DefaultArena::WbemMemFree(v28);
                  throw;
                }
              }
              goto LABEL_36;
            }
            break;
          case 7u:
            v11 = v10 - 2;
            if ( cbData >= (unsigned int)v11 )
            {
              *((_BYTE *)v9 + v11) = 0;
              v12 = v10 - 1;
            }
            else
            {
              *((_BYTE *)v9 + cbData) = 0;
              v12 = cbData + 1;
            }
            *((_BYTE *)v9 + v12) = 0;
            v13 = v9;
            v14 = -1;
            do
              ++v14;
            while ( v9[v14] );
            for ( i = v14; (_DWORD)v14 && i <= v10; i += v14 )
            {
              CHString::operator+=(a4, v13);
              CHString::operator+=(a4, L"\n");
              v13 += (int)v14 + 1;
              v14 = -1;
              do
                ++v14;
              while ( v13[v14] );
            }
LABEL_36:
            CWin32DefaultArena::WbemMemFree(v9);
            return 0;
        }
      }
      CWin32DefaultArena::WbemMemFree(v9);
      v27 = 0;
      return 2147746131LL;
    }
  }
  return 2147746131LL;
}

```

## disassembly

```asm
0x140012720  push    rbx
0x140012722  push    rsi
0x140012723  push    rdi
0x140012724  push    r12
0x140012726  push    r13
0x140012728  push    r14
0x14001272a  push    r15
0x14001272c  sub     rsp, 50h
0x140012730  mov     rsi, r9
0x140012733  mov     rdi, r8
0x140012736  mov     r15, rdx
0x140012739  mov     r12, rcx
0x14001273c  xor     r13d, r13d
0x14001273f  mov     [rsp+88h+cbData], r13d
0x140012744  mov     [rsp+88h+Type], r13d
0x140012749  lea     rdx, qword_14001BC40; unsigned __int16 *
0x140012750  mov     rcx, r9; this
0x140012753  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x140012758  lea     rax, [rsp+88h+cbData]
0x14001275d  mov     [rsp+88h+lpcbData], rax; lpcbData
0x140012762  mov     [rsp+88h+lpData], r13; lpData
0x140012767  lea     r9, [rsp+88h+Type]; lpType
0x14001276c  xor     r8d, r8d; lpReserved
0x14001276f  mov     rdx, rdi; lpValueName
0x140012772  mov     rcx, r15; hKey
0x140012775  call    cs:__imp_RegQueryValueExW
0x14001277b  test    eax, eax
0x14001277d  jnz     loc_1400129DC
0x140012783  mov     ecx, [rsp+88h+cbData]
0x140012787  test    ecx, ecx
0x140012789  jz      loc_1400129DC
0x14001278f  mov     edx, [rsp+88h+Type]
0x140012793  lea     eax, [rdx-1]
0x140012796  cmp     eax, 1
0x140012799  jbe     short loc_1400127A0
0x14001279b  cmp     edx, 7
0x14001279e  jnz     short loc_1400127A7
0x1400127a0  add     ecx, 2
0x1400127a3  mov     [rsp+88h+cbData], ecx
0x1400127a7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1400127ad  mov     rbx, rax
0x1400127b0  mov     [rsp+88h+var_48], rax
0x1400127b5  mov     r14d, [rsp+88h+cbData]
0x1400127ba  test    rax, rax
0x1400127bd  jnz     short loc_1400127D6
0x1400127bf  mov     [rsp+88h+pExceptionObject], r13d
0x1400127c4  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x1400127cb  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1400127d0  call    _CxxThrowException_0
0x1400127d6  lea     rax, [rsp+88h+cbData]
0x1400127db  mov     [rsp+88h+lpcbData], rax; unsigned int *
0x1400127e0  lea     rax, [rsp+88h+Type]
0x1400127e5  mov     [rsp+88h+lpData], rax; unsigned int *
0x1400127ea  mov     r9, rbx; void *
0x1400127ed  mov     r8, rdi; unsigned __int16 *
0x1400127f0  mov     rdx, r15; HKEY
0x1400127f3  mov     rcx, r12; this
0x1400127f6  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x1400127fb  test    eax, eax
0x1400127fd  jz      short loc_140012817
0x1400127ff  mov     rcx, rbx
0x140012802  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140012808  mov     [rsp+88h+var_48], r13
0x14001280d  mov     eax, 80040153h
0x140012812  jmp     loc_1400129E1
0x140012817  mov     eax, [rsp+88h+Type]
0x14001281b  sub     eax, 1
0x14001281e  jz      loc_1400129AE
0x140012824  sub     eax, 1
0x140012827  jz      loc_1400129AE
0x14001282d  sub     eax, 1
0x140012830  jz      loc_140012960
0x140012836  sub     eax, 1
0x140012839  jz      loc_1400128DE
0x14001283f  cmp     eax, 3
0x140012842  jz      short loc_14001285C
0x140012844  mov     rcx, rbx
0x140012847  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14001284d  mov     [rsp+88h+var_48], r13
0x140012852  mov     eax, 80040153h
0x140012857  jmp     loc_1400129E1
0x14001285c  lea     eax, [r14-2]
0x140012860  cmp     [rsp+88h+cbData], eax
0x140012864  jnb     short loc_140012876
0x140012866  mov     eax, [rsp+88h+cbData]
0x14001286a  mov     [rax+rbx], r13b
0x14001286e  mov     eax, [rsp+88h+cbData]
0x140012872  inc     eax
0x140012874  jmp     short loc_14001287E
0x140012876  mov     [rax+rbx], r13b
0x14001287a  lea     eax, [r14-1]
0x14001287e  mov     [rax+rbx], r13b
0x140012882  mov     r15, rbx
0x140012885  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140012889  inc     rdi
0x14001288c  cmp     [rbx+rdi*2], r13w
0x140012891  jnz     short loc_140012889
0x140012893  mov     r12d, edi
0x140012896  test    edi, edi
0x140012898  jz      loc_1400129CF
0x14001289e  cmp     r12d, r14d
0x1400128a1  ja      loc_1400129CF
0x1400128a7  mov     rdx, r15; unsigned __int16 *
0x1400128aa  mov     rcx, rsi; this
0x1400128ad  call    ??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x1400128b2  lea     rdx, asc_14001BCF8; "\n"
0x1400128b9  mov     rcx, rsi; this
0x1400128bc  call    ??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x1400128c1  lea     eax, [rdi+1]
0x1400128c4  movsxd  rcx, eax
0x1400128c7  lea     r15, [r15+rcx*2]
0x1400128cb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400128cf  inc     rdi
0x1400128d2  cmp     [r15+rdi*2], r13w
0x1400128d7  jnz     short loc_1400128CF
0x1400128d9  add     r12d, edi
0x1400128dc  jmp     short loc_140012896
0x1400128de  cmp     [rsp+88h+cbData], 4
0x1400128e3  jz      short loc_1400128FD
0x1400128e5  mov     rcx, rbx
0x1400128e8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400128ee  mov     [rsp+88h+var_48], r13
0x1400128f3  mov     eax, 80040153h
0x1400128f8  jmp     loc_1400129E1
0x1400128fd  mov     ecx, 200h
0x140012902  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140012908  mov     rdi, rax
0x14001290b  mov     [rsp+88h+var_40], rax
0x140012910  test    rax, rax
0x140012913  jz      short loc_14001294A
0x140012915  mov     r9d, [rbx]
0x140012918  lea     r8, aLd; "%ld"
0x14001291f  mov     edx, 100h; unsigned __int64
0x140012924  mov     rcx, rax; unsigned __int16 *
0x140012927  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001292c  mov     rdx, rdi; unsigned __int16 *
0x14001292f  mov     rcx, rsi; this
0x140012932  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x140012937  mov     rcx, rdi
0x14001293a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140012940  mov     [rsp+88h+var_40], r13
0x140012945  jmp     loc_1400129CF
0x14001294a  mov     [rsp+88h+var_4C], r13d
0x14001294f  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x140012956  lea     rcx, [rsp+88h+var_4C]; pExceptionObject
0x14001295b  call    _CxxThrowException_0
0x140012960  mov     rcx, rsi; this
0x140012963  call    ?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
0x140012968  mov     eax, [rsp+88h+cbData]
0x14001296c  mov     edi, eax
0x14001296e  and     edi, 1
0x140012971  shr     eax, 1
0x140012973  lea     r14d, [rax+rdi]
0x140012977  mov     edx, r14d; int
0x14001297a  mov     rcx, rsi; this
0x14001297d  call    ?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x140012982  mov     r8d, [rsp+88h+cbData]; Size
0x140012987  mov     rdx, rbx; Src
0x14001298a  mov     rcx, rax; void *
0x14001298d  call    memcpy_0
0x140012992  test    edi, edi
0x140012994  jz      short loc_1400129A1
0x140012996  mov     ecx, [rsp+88h+cbData]
0x14001299a  mov     rax, [rsi]
0x14001299d  mov     [rcx+rax], r13b
0x1400129a1  mov     edx, r14d; int
0x1400129a4  mov     rcx, rsi; this
0x1400129a7  call    ?GetBufferSetLength@CHString@@QEAAPEAGH@Z; CHString::GetBufferSetLength(int)
0x1400129ac  jmp     short loc_1400129CF
0x1400129ae  cmp     [rsp+88h+cbData], r14d
0x1400129b3  jnb     short loc_1400129BB
0x1400129b5  mov     eax, [rsp+88h+cbData]
0x1400129b9  jmp     short loc_1400129BF
0x1400129bb  lea     eax, [r14-1]
0x1400129bf  mov     [rax+rbx], r13b
0x1400129c3  mov     rdx, rbx; unsigned __int16 *
0x1400129c6  mov     rcx, rsi; this
0x1400129c9  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x1400129ce  nop
0x1400129cf  mov     rcx, rbx
0x1400129d2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400129d8  xor     eax, eax
0x1400129da  jmp     short loc_1400129E1
0x1400129dc  mov     eax, 80040153h
0x1400129e1  add     rsp, 50h
0x1400129e5  pop     r15
0x1400129e7  pop     r14
0x1400129e9  pop     r13
0x1400129eb  pop     r12
0x1400129ed  pop     rdi
0x1400129ee  pop     rsi
0x1400129ef  pop     rbx
0x1400129f0  retn
```
