# StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)

- ea: `0x14000e1dc`
- end: `0x14000e3e1`
- name: `?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z`
- size: `517`
- prototype: `void __fastcall(StartList *this, unsigned __int16 *, unsigned int, unsigned __int16 *, DWORD Type, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ee8c`

## callees

- `0x14000bda8`
- `0x14000bdf4`
- `0x14000bf04`
- `0x14000e1dc`
- `0x140010bbc`
- `0x140015ace`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14000e2f3`
- `ADVAPI32!RegQueryValueExW` at `0x14000e2f3`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e23e`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e23e`
- `ADVAPI32!RegCloseKey` at `0x14000e25e`
- `ADVAPI32!RegCloseKey` at `0x14000e25e`
- `KERNEL32!RegSetValueExW` at `0x14000e354`
- `KERNEL32!RegSetValueExW` at `0x14000e354`

## string_xrefs

- `0x14000e230`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
void __fastcall StartList::GetTempValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        DWORD Type,
        HKEY *a6)
{
  LSTATUS v9; // eax
  HKEY *v10; // rdi
  _QWORD *v11; // rbx
  LPCWSTR *v12; // rsi
  unsigned int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  _BYTE v17[400]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int Data; // [rsp+1E0h] [rbp+E0h] BYREF

  Data = a3;
  *a2 = 0;
  *a4 = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
          0,
          0x2001Fu,
          &phkResult) )
  {
    v9 = 0;
    v10 = a6;
    if ( *a6 )
      v9 = RegCloseKey(*a6);
    *v10 = phkResult;
    if ( !v9 )
    {
      Data = 0;
      ATManager::ATManager((ATManager *)v17);
      v11 = *(_QWORD **)ATManager::GetAccommodations(v17);
      while ( v11 )
      {
        v12 = (LPCWSTR *)v11[2];
        v11 = (_QWORD *)*v11;
        if ( wcscmp_0(v12[5], L"SystemSetting") )
        {
          Type = 0;
          LODWORD(phkResult) = 4;
          if ( !RegQueryValueExW(*v10, *v12, 0, &Type, (LPBYTE)&Data, (LPDWORD)&phkResult) && Type == 4 )
          {
            v13 = Data;
            if ( (Data & 2) != 0 )
            {
              *((_DWORD *)this + 74) = 1;
              Data = v13 & 0xFFFFFFFD;
              Type = v13 & 0xFFFFFFFD;
              RegSetValueExW(*v10, *v12, 0, 4u, (const BYTE *)&Type, 4u);
              v15 = -1;
              if ( (Data & 1) != 0 )
              {
                do
                  ++v15;
                while ( a2[v15] );
                if ( v15 )
                  StringCbCatW(a2, v14, L",");
                v16 = a2;
              }
              else
              {
                do
                  ++v15;
                while ( a4[v15] );
                if ( v15 )
                  StringCbCatW(a4, v14, L",");
                v16 = a4;
              }
              StringCbCatW(v16, v14, *v12);
            }
          }
        }
      }
      ATManager::~ATManager((ATManager *)v17);
    }
  }
}

```

## disassembly

```asm
0x14000e1dc  mov     [rsp-8+arg_0], rbx
0x14000e1e1  mov     [rsp-8+Data], r8d
0x14000e1e6  push    rbp
0x14000e1e7  push    rsi
0x14000e1e8  push    rdi
0x14000e1e9  push    r12
0x14000e1eb  push    r13
0x14000e1ed  push    r14
0x14000e1ef  push    r15
0x14000e1f1  lea     rbp, [rsp-90h]
0x14000e1f9  sub     rsp, 190h
0x14000e200  mov     r14, r9
0x14000e203  mov     r15, rdx
0x14000e206  mov     r13, rcx
0x14000e209  xor     r12d, r12d
0x14000e20c  mov     [rdx], r12w
0x14000e210  mov     [r9], r12w
0x14000e214  mov     [rbp+0C0h+arg_8], r12
0x14000e21b  lea     rax, [rbp+0C0h+arg_8]
0x14000e222  mov     [rsp+1C0h+phkResult], rax; phkResult
0x14000e227  mov     r9d, 2001Fh; samDesired
0x14000e22d  xor     r8d, r8d; ulOptions
0x14000e230  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000e237  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000e23e  call    cs:__imp_RegOpenKeyExW
0x14000e244  test    eax, eax
0x14000e246  jnz     loc_14000E3C6
0x14000e24c  mov     eax, r12d
0x14000e24f  mov     rdi, [rbp+0C0h+arg_28]
0x14000e256  mov     rcx, [rdi]; hKey
0x14000e259  test    rcx, rcx
0x14000e25c  jz      short loc_14000E264
0x14000e25e  call    cs:__imp_RegCloseKey
0x14000e264  mov     rcx, [rbp+0C0h+arg_8]
0x14000e26b  mov     [rdi], rcx
0x14000e26e  test    eax, eax
0x14000e270  jnz     loc_14000E3C6
0x14000e276  mov     [rbp+0C0h+Data], r12d
0x14000e27d  lea     rcx, [rsp+1C0h+var_190]; this
0x14000e282  call    ??0ATManager@@QEAA@XZ; ATManager::ATManager(void)
0x14000e287  nop
0x14000e288  lea     rcx, [rsp+1C0h+var_190]
0x14000e28d  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x14000e292  mov     rbx, [rax]
0x14000e295  jmp     loc_14000E3B3
0x14000e29a  mov     rsi, [rbx+10h]
0x14000e29e  mov     rbx, [rbx]
0x14000e2a1  lea     rdx, aSystemsetting; "SystemSetting"
0x14000e2a8  mov     rcx, [rsi+28h]; String1
0x14000e2ac  call    wcscmp_0
0x14000e2b1  nop
0x14000e2b2  test    eax, eax
0x14000e2b4  jz      loc_14000E3B3
0x14000e2ba  mov     [rbp+0C0h+Type], r12d
0x14000e2c1  mov     dword ptr [rbp+0C0h+arg_8], 4
0x14000e2cb  lea     rax, [rbp+0C0h+arg_8]
0x14000e2d2  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x14000e2d7  lea     rax, [rbp+0C0h+Data]
0x14000e2de  mov     [rsp+1C0h+phkResult], rax; lpData
0x14000e2e3  lea     r9, [rbp+0C0h+Type]; lpType
0x14000e2ea  xor     r8d, r8d; lpReserved
0x14000e2ed  mov     rdx, [rsi]; lpValueName
0x14000e2f0  mov     rcx, [rdi]; hKey
0x14000e2f3  call    cs:__imp_RegQueryValueExW
0x14000e2f9  test    eax, eax
0x14000e2fb  jnz     loc_14000E3B3
0x14000e301  lea     ecx, [rax+4]
0x14000e304  cmp     [rbp+0C0h+Type], ecx
0x14000e30a  jnz     loc_14000E3B3
0x14000e310  mov     eax, [rbp+0C0h+Data]
0x14000e316  test    al, 2
0x14000e318  jz      loc_14000E3B3
0x14000e31e  mov     dword ptr [r13+128h], 1
0x14000e329  and     eax, 0FFFFFFFDh
0x14000e32c  mov     [rbp+0C0h+Data], eax
0x14000e332  mov     [rbp+0C0h+Type], eax
0x14000e338  mov     dword ptr [rsp+1C0h+lpcbData], ecx; cbData
0x14000e33c  lea     rax, [rbp+0C0h+Type]
0x14000e343  mov     [rsp+1C0h+phkResult], rax; lpData
0x14000e348  mov     r9d, ecx; dwType
0x14000e34b  xor     r8d, r8d; Reserved
0x14000e34e  mov     rdx, [rsi]; lpValueName
0x14000e351  mov     rcx, [rdi]; hKey
0x14000e354  call    cs:__imp_RegSetValueExW
0x14000e35a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e35e  test    byte ptr [rbp+0C0h+Data], 1
0x14000e365  jz      short loc_14000E38A
0x14000e367  inc     rax
0x14000e36a  cmp     [r15+rax*2], r12w
0x14000e36f  jnz     short loc_14000E367
0x14000e371  test    rax, rax
0x14000e374  jz      short loc_14000E385
0x14000e376  lea     r8, asc_140019790; ","
0x14000e37d  mov     rcx, r15; unsigned __int16 *
0x14000e380  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000e385  mov     rcx, r15
0x14000e388  jmp     short loc_14000E3AB
0x14000e38a  inc     rax
0x14000e38d  cmp     [r14+rax*2], r12w
0x14000e392  jnz     short loc_14000E38A
0x14000e394  test    rax, rax
0x14000e397  jz      short loc_14000E3A8
0x14000e399  lea     r8, asc_140019790; ","
0x14000e3a0  mov     rcx, r14; unsigned __int16 *
0x14000e3a3  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000e3a8  mov     rcx, r14; unsigned __int16 *
0x14000e3ab  mov     r8, [rsi]; unsigned __int16 *
0x14000e3ae  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000e3b3  test    rbx, rbx
0x14000e3b6  jnz     loc_14000E29A
0x14000e3bc  lea     rcx, [rsp+1C0h+var_190]; this
0x14000e3c1  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14000e3c6  mov     rbx, [rsp+1C0h+arg_0]
0x14000e3ce  add     rsp, 190h
0x14000e3d5  pop     r15
0x14000e3d7  pop     r14
0x14000e3d9  pop     r13
0x14000e3db  pop     r12
0x14000e3dd  pop     rdi
0x14000e3de  pop     rsi
0x14000e3df  pop     rbp
0x14000e3e0  retn
```
