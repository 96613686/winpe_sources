# CManagedAppProcessor::Process(void)

- ea: `0x180011ac0`
- end: `0x180011e3e`
- name: `?Process@CManagedAppProcessor@@QEAAKXZ`
- size: `894`
- prototype: `DWORD __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b7e8`

## callees

- `0x18000ac90`
- `0x18000ca60`
- `0x18000cb98`
- `0x18000cc10`
- `0x18000f634`
- `0x18000f8bc`
- `0x1800101fc`
- `0x1800116e4`
- `0x180011ac0`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011c62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011e07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011c62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011e07`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011b85`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011b85`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011af7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d71`

## pseudocode

```c
DWORD __fastcall CManagedAppProcessor::Process(const unsigned __int16 **this)
{
  DWORD LastError; // eax
  DWORD result; // eax
  int AppsFromDirectory; // edi
  const unsigned __int16 **v5; // rdx
  _DWORD *v6; // rsi
  unsigned int v7; // edx
  const unsigned __int16 **v8; // r8
  unsigned int v9; // r14d
  const unsigned __int16 **v10; // rdx
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  SIZE_T v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *lpData; // rsi
  const unsigned __int16 **v16; // rcx

  if ( *((_DWORD *)this + 99) == 1 || !*((_DWORD *)this + 74) || ImpersonateLoggedOnUser((HANDLE)this[33]) )
  {
    AppsFromDirectory = 0;
    goto LABEL_9;
  }
  if ( *(_DWORD *)&gDebugLevel )
  {
    LastError = GetLastError();
    _DebugMsg(2, 0xBC4u, LastError);
  }
  result = GetLastError();
  AppsFromDirectory = result;
  if ( !result )
  {
LABEL_9:
    v5 = (const unsigned __int16 **)this[1];
    this[3] = this[2];
    while ( 1 )
    {
      this[2] = (const unsigned __int16 *)v5;
      if ( v5 == this )
        v5 = 0;
      if ( !v5 )
        break;
      AppsFromDirectory = (unsigned int)CSPath::AddComponent((HLOCAL *)this + 30, v5[4], v5[3]);
      if ( AppsFromDirectory )
        break;
      v5 = (const unsigned __int16 **)*((_QWORD *)this[2] + 1);
    }
    if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
      RevertToSelf();
    this[2] = this[3];
    if ( *((_DWORD *)this + 99) != 1
      && (AppsFromDirectory || (AppsFromDirectory = CSPath::Commit((CSPath *)(this + 30), (void *)this[33])) != 0) )
    {
      if ( AppsFromDirectory == -2147221144 )
        return 0;
      *((_DWORD *)this + 88) = 1;
      return AppsFromDirectory;
    }
    if ( *((_DWORD *)this + 75) )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xBCDu);
      if ( AppsFromDirectory )
        goto LABEL_28;
    }
    else
    {
      if ( *((_DWORD *)this + 99) != 1 )
        CManagedAppProcessor::LogonMsg((CManagedAppProcessor *)this, 0x3E8u);
      AppsFromDirectory = CManagedAppProcessor::GetAppsFromDirectory((CManagedAppProcessor *)this);
      if ( AppsFromDirectory )
        goto LABEL_28;
    }
    AppsFromDirectory = CManagedAppProcessor::GetAppsFromLocal((CManagedAppProcessor *)this);
    if ( !AppsFromDirectory )
    {
      if ( *((_DWORD *)this + 99) != 1 )
      {
        v8 = (const unsigned __int16 **)this[1];
        v9 = 1;
        v10 = v8;
        this[3] = this[2];
        if ( v8 == this )
          v10 = 0;
        while ( 1 )
        {
          this[2] = (const unsigned __int16 *)v8;
          if ( !v10 )
            break;
          v11 = v10[2];
          if ( v11 )
          {
            v12 = -1;
            do
              ++v12;
            while ( v11[v12] );
          }
          else
          {
            LODWORD(v12) = 0;
          }
          v8 = (const unsigned __int16 **)v8[1];
          v9 += v12 + 1;
          v10 = v8;
          if ( v8 == this )
            v10 = 0;
        }
        this[2] = this[3];
        v13 = 2LL * v9;
        if ( !is_mul_ok(v9, 2u) )
          v13 = -1;
        v14 = (unsigned __int16 *)LocalAlloc(0, v13);
        lpData = v14;
        if ( !v14 )
        {
          AppsFromDirectory = 14;
          goto LABEL_28;
        }
        *v14 = 0;
        v16 = (const unsigned __int16 **)this[1];
        this[3] = this[2];
        while ( 1 )
        {
          this[2] = (const unsigned __int16 *)v16;
          if ( v16 == this )
            v16 = 0;
          if ( !v16 )
            break;
          AppsFromDirectory = StringCchCatW(lpData, v9, v16[2]);
          if ( AppsFromDirectory < 0 )
            goto LABEL_71;
          AppsFromDirectory = StringCchCatW(lpData, v9, L";");
          if ( AppsFromDirectory < 0 )
            goto LABEL_71;
          v16 = (const unsigned __int16 **)*((_QWORD *)this[2] + 1);
        }
        this[2] = this[3];
        AppsFromDirectory = RegSetValueExW((HKEY)this[36], L"GPOs", 0, 1u, (const BYTE *)lpData, 2 * v9);
LABEL_71:
        LocalFree(lpData);
        if ( AppsFromDirectory )
          goto LABEL_28;
      }
      AppsFromDirectory = CManagedAppProcessor::GetLostApps((CManagedAppProcessor *)this);
      if ( !AppsFromDirectory )
      {
        v6 = this + 44;
        AppsFromDirectory = CAppList::ProcessPolicy((CAppList *)(this + 4));
        if ( !AppsFromDirectory )
          goto LABEL_31;
        goto LABEL_30;
      }
    }
LABEL_28:
    v6 = this + 44;
    *((_DWORD *)this + 88) = 3;
LABEL_30:
    *v6 = 4;
LABEL_31:
    if ( *((_DWORD *)this + 99) != 1 )
    {
      if ( !AppsFromDirectory && *((_DWORD *)this + 80) )
        RegSetValueExW((HKEY)this[36], L"LastArchLang", 0, 4u, (const BYTE *)this + 320, 4u);
      if ( !*((_DWORD *)this + 75) )
      {
        v7 = 1101;
        if ( !*((_DWORD *)this + 74) )
          v7 = 1100;
        CManagedAppProcessor::LogonMsg((CManagedAppProcessor *)this, v7);
      }
    }
    if ( !AppsFromDirectory && *((_DWORD *)this + 76) && !*((_DWORD *)this + 75) )
      return 1274;
    return AppsFromDirectory;
  }
  return result;
}

```

## disassembly

```asm
0x180011ac0  push    rbx
0x180011ac2  push    rbp
0x180011ac3  push    rsi
0x180011ac4  push    rdi
0x180011ac5  push    r12
0x180011ac7  push    r14
0x180011ac9  push    r15
0x180011acb  sub     rsp, 30h
0x180011acf  mov     esi, 2
0x180011ad4  xor     r15d, r15d
0x180011ad7  mov     rbx, rcx
0x180011ada  lea     r12d, [rsi-1]
0x180011ade  cmp     [rcx+18Ch], r12d
0x180011ae5  jz      short loc_180011B30
0x180011ae7  cmp     [rcx+128h], r15d
0x180011aee  jz      short loc_180011B30
0x180011af0  mov     rcx, [rcx+108h]; hToken
0x180011af7  call    cs:__imp_ImpersonateLoggedOnUser
0x180011afd  test    eax, eax
0x180011aff  jnz     short loc_180011B30
0x180011b01  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180011b08  jz      short loc_180011B1F
0x180011b0a  call    cs:__imp_GetLastError
0x180011b10  mov     edx, 0BC4h; unsigned int
0x180011b15  mov     ecx, esi; unsigned int
0x180011b17  mov     r8d, eax
0x180011b1a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180011b1f  call    cs:__imp_GetLastError
0x180011b25  mov     edi, eax
0x180011b27  test    eax, eax
0x180011b29  jz      short loc_180011B33
0x180011b2b  jmp     loc_180011CAA
0x180011b30  mov     edi, r15d
0x180011b33  mov     rax, [rbx+10h]
0x180011b37  mov     rdx, [rbx+8]
0x180011b3b  mov     [rbx+18h], rax
0x180011b3f  cmp     rdx, rbx
0x180011b42  mov     [rbx+10h], rdx
0x180011b46  cmovz   rdx, r15
0x180011b4a  test    rdx, rdx
0x180011b4d  jz      short loc_180011B73
0x180011b4f  mov     r8, [rdx+18h]; unsigned __int16 *
0x180011b53  lea     rcx, [rbx+0F0h]; this
0x180011b5a  mov     rdx, [rdx+20h]; unsigned __int16 *
0x180011b5e  call    ?AddComponent@CSPath@@QEAAKPEBG0@Z; CSPath::AddComponent(ushort const *,ushort const *)
0x180011b63  mov     edi, eax
0x180011b65  test    eax, eax
0x180011b67  jnz     short loc_180011B73
0x180011b69  mov     rax, [rbx+10h]
0x180011b6d  mov     rdx, [rax+8]
0x180011b71  jmp     short loc_180011B3F
0x180011b73  cmp     [rbx+18Ch], r12d
0x180011b7a  jz      short loc_180011B8B
0x180011b7c  cmp     [rbx+128h], r15d
0x180011b83  jz      short loc_180011B8B
0x180011b85  call    cs:__imp_RevertToSelf
0x180011b8b  mov     rax, [rbx+18h]
0x180011b8f  mov     [rbx+10h], rax
0x180011b93  cmp     [rbx+18Ch], r12d
0x180011b9a  jz      short loc_180011BD4
0x180011b9c  test    edi, edi
0x180011b9e  jnz     short loc_180011BB9
0x180011ba0  mov     rdx, [rbx+108h]; void *
0x180011ba7  lea     rcx, [rbx+0F0h]; this
0x180011bae  call    ?Commit@CSPath@@QEAAKPEAX@Z; CSPath::Commit(void *)
0x180011bb3  mov     edi, eax
0x180011bb5  test    eax, eax
0x180011bb7  jz      short loc_180011BD4
0x180011bb9  cmp     edi, 80040168h
0x180011bbf  jnz     short loc_180011BC8
0x180011bc1  xor     eax, eax
0x180011bc3  jmp     loc_180011CAA
0x180011bc8  mov     [rbx+160h], r12d
0x180011bcf  jmp     loc_180011CA8
0x180011bd4  cmp     [rbx+12Ch], r15d
0x180011bdb  jz      loc_180011CB9
0x180011be1  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180011be8  jz      short loc_180011BF9
0x180011bea  mov     edx, 0BCDh; unsigned int
0x180011bef  mov     ecx, 4; unsigned int
0x180011bf4  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180011bf9  test    edi, edi
0x180011bfb  jz      loc_180011CE1
0x180011c01  lea     rsi, [rbx+160h]
0x180011c08  mov     dword ptr [rsi], 3
0x180011c0e  test    edi, edi
0x180011c10  jnz     short loc_180011C21
0x180011c12  lea     rcx, [rbx+20h]; this
0x180011c16  call    ?ProcessPolicy@CAppList@@QEAAKXZ; CAppList::ProcessPolicy(void)
0x180011c1b  mov     edi, eax
0x180011c1d  test    eax, eax
0x180011c1f  jz      short loc_180011C27
0x180011c21  mov     dword ptr [rsi], 4
0x180011c27  cmp     [rbx+18Ch], r12d
0x180011c2e  jz      short loc_180011C8C
0x180011c30  test    edi, edi
0x180011c32  jnz     short loc_180011C68
0x180011c34  lea     rax, [rbx+140h]
0x180011c3b  cmp     [rax], r15d
0x180011c3e  jz      short loc_180011C68
0x180011c40  mov     rcx, [rbx+120h]; hKey
0x180011c47  lea     r9d, [rdi+4]; dwType
0x180011c4b  mov     [rsp+68h+cbData], 4; cbData
0x180011c53  lea     rdx, aLastarchlang; "LastArchLang"
0x180011c5a  xor     r8d, r8d; Reserved
0x180011c5d  mov     [rsp+68h+lpData], rax; lpData
0x180011c62  call    cs:__imp_RegSetValueExW
0x180011c68  cmp     [rbx+12Ch], r15d
0x180011c6f  jnz     short loc_180011C8C
0x180011c71  mov     rcx, rbx; this
0x180011c74  mov     edx, 44Dh
0x180011c79  cmp     [rbx+128h], r15d
0x180011c80  jnz     short loc_180011C87
0x180011c82  mov     edx, 44Ch; unsigned int
0x180011c87  call    ?LogonMsg@CManagedAppProcessor@@AEAAXKZZ; CManagedAppProcessor::LogonMsg(ulong,...)
0x180011c8c  test    edi, edi
0x180011c8e  jnz     short loc_180011CA8
0x180011c90  cmp     [rbx+130h], r15d
0x180011c97  jz      short loc_180011CA8
0x180011c99  cmp     [rbx+12Ch], r15d
0x180011ca0  mov     eax, 4FAh
0x180011ca5  cmovz   edi, eax
0x180011ca8  mov     eax, edi
0x180011caa  add     rsp, 30h
0x180011cae  pop     r15
0x180011cb0  pop     r14
0x180011cb2  pop     r12
0x180011cb4  pop     rdi
0x180011cb5  pop     rsi
0x180011cb6  pop     rbp
0x180011cb7  pop     rbx
0x180011cb8  retn
0x180011cb9  cmp     [rbx+18Ch], r12d
0x180011cc0  jz      short loc_180011CCF
0x180011cc2  mov     edx, 3E8h; unsigned int
0x180011cc7  mov     rcx, rbx; this
0x180011cca  call    ?LogonMsg@CManagedAppProcessor@@AEAAXKZZ; CManagedAppProcessor::LogonMsg(ulong,...)
0x180011ccf  mov     rcx, rbx; this
0x180011cd2  call    ?GetAppsFromDirectory@CManagedAppProcessor@@AEAAJXZ; CManagedAppProcessor::GetAppsFromDirectory(void)
0x180011cd7  mov     edi, eax
0x180011cd9  test    eax, eax
0x180011cdb  jnz     loc_180011C01
0x180011ce1  mov     rcx, rbx; this
0x180011ce4  call    ?GetAppsFromLocal@CManagedAppProcessor@@AEAAKXZ; CManagedAppProcessor::GetAppsFromLocal(void)
0x180011ce9  mov     edi, eax
0x180011ceb  test    eax, eax
0x180011ced  jnz     loc_180011C01
0x180011cf3  cmp     [rbx+18Ch], r12d
0x180011cfa  jz      loc_180011E20
0x180011d00  mov     r8, [rbx+8]
0x180011d04  mov     r14d, r12d
0x180011d07  mov     rax, [rbx+10h]
0x180011d0b  cmp     r8, rbx
0x180011d0e  mov     rdx, r8
0x180011d11  mov     [rbx+18h], rax
0x180011d15  cmovz   rdx, r15
0x180011d19  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011d1d  jmp     short loc_180011D4E
0x180011d1f  mov     rcx, [rdx+10h]
0x180011d23  test    rcx, rcx
0x180011d26  jnz     short loc_180011D2D
0x180011d28  mov     rax, r15
0x180011d2b  jmp     short loc_180011D3A
0x180011d2d  mov     rax, r9
0x180011d30  inc     rax
0x180011d33  cmp     [rcx+rax*2], r15w
0x180011d38  jnz     short loc_180011D30
0x180011d3a  mov     r8, [r8+8]
0x180011d3e  inc     r14d
0x180011d41  add     r14d, eax
0x180011d44  mov     rdx, r8
0x180011d47  cmp     r8, rbx
0x180011d4a  cmovz   rdx, r15
0x180011d4e  mov     [rbx+10h], r8
0x180011d52  test    rdx, rdx
0x180011d55  jnz     short loc_180011D1F
0x180011d57  mov     rcx, [rbx+18h]
0x180011d5b  mov     rax, rsi
0x180011d5e  mov     [rbx+10h], rcx
0x180011d62  mov     ebp, r14d
0x180011d65  mul     rbp
0x180011d68  cmovb   rax, r9
0x180011d6c  xor     ecx, ecx; uFlags
0x180011d6e  mov     rdx, rax; uBytes
0x180011d71  call    cs:__imp_LocalAlloc
0x180011d77  mov     rsi, rax
0x180011d7a  test    rax, rax
0x180011d7d  jnz     short loc_180011D87
0x180011d7f  lea     edi, [rax+0Eh]
0x180011d82  jmp     loc_180011C01
0x180011d87  mov     [rax], r15w
0x180011d8b  mov     rax, [rbx+10h]
0x180011d8f  mov     rcx, [rbx+8]
0x180011d93  mov     [rbx+18h], rax
0x180011d97  jmp     short loc_180011DCE
0x180011d99  mov     r8, [rcx+10h]; unsigned __int16 *
0x180011d9d  mov     rdx, rbp; unsigned __int64
0x180011da0  mov     rcx, rsi; unsigned __int16 *
0x180011da3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011da8  mov     edi, eax
0x180011daa  test    eax, eax
0x180011dac  js      short loc_180011E0F
0x180011dae  lea     r8, asc_18002FEBC; ";"
0x180011db5  mov     rdx, rbp; unsigned __int64
0x180011db8  mov     rcx, rsi; unsigned __int16 *
0x180011dbb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011dc0  mov     edi, eax
0x180011dc2  test    eax, eax
0x180011dc4  js      short loc_180011E0F
0x180011dc6  mov     rax, [rbx+10h]
0x180011dca  mov     rcx, [rax+8]
0x180011dce  cmp     rcx, rbx
0x180011dd1  mov     [rbx+10h], rcx
0x180011dd5  cmovz   rcx, r15
0x180011dd9  test    rcx, rcx
0x180011ddc  jnz     short loc_180011D99
0x180011dde  mov     rax, [rbx+18h]
0x180011de2  lea     rdx, aGpos; "GPOs"
0x180011de9  mov     [rbx+10h], rax
0x180011ded  mov     r9d, r12d; dwType
0x180011df0  mov     rcx, [rbx+120h]; hKey
0x180011df7  lea     eax, [r14+r14]
0x180011dfb  mov     [rsp+68h+cbData], eax; cbData
0x180011dff  xor     r8d, r8d; Reserved
0x180011e02  mov     [rsp+68h+lpData], rsi; lpData
0x180011e07  call    cs:__imp_RegSetValueExW
0x180011e0d  mov     edi, eax
0x180011e0f  mov     rcx, rsi; hMem
0x180011e12  call    cs:__imp_LocalFree
0x180011e18  test    edi, edi
0x180011e1a  jnz     loc_180011C01
0x180011e20  mov     rcx, rbx; this
0x180011e23  call    ?GetLostApps@CManagedAppProcessor@@AEAAKXZ; CManagedAppProcessor::GetLostApps(void)
0x180011e28  mov     edi, eax
0x180011e2a  test    eax, eax
0x180011e2c  jnz     loc_180011C01
0x180011e32  lea     rsi, [rbx+160h]
0x180011e39  jmp     loc_180011C12
```
