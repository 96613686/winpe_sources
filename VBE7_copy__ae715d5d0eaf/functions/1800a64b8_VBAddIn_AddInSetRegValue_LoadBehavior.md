# VBAddIn::AddInSetRegValue(LoadBehavior)

- ea: `0x1800a64b8`
- end: `0x1800a6674`
- name: `?AddInSetRegValue@VBAddIn@@AEAAJW4LoadBehavior@@@Z`
- size: `444`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a4fc0`
- `0x1800a58b0`
- `0x1800a5dec`

## callees

- `0x18001606c`
- `0x1800a64b8`
- `0x1800a7178`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x1800a6653`
- `MSVCR100!free` at `0x1800a6661`
- `MSVCR100!free` at `0x1800a6653`
- `MSVCR100!free` at `0x1800a6661`
- `MSVCR100!malloc` at `0x1800a651d`
- `MSVCR100!malloc` at `0x1800a651d`
- `KERNEL32!lstrlenA` at `0x1800a6503`
- `KERNEL32!lstrlenA` at `0x1800a650f`
- `KERNEL32!lstrlenA` at `0x1800a6503`
- `KERNEL32!lstrlenA` at `0x1800a650f`
- `USER32!wsprintfA` at `0x1800a6540`
- `USER32!wsprintfA` at `0x1800a6540`
- `ADVAPI32!RegSetValueExA` at `0x1800a6613`
- `ADVAPI32!RegSetValueExA` at `0x1800a6613`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a6562`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a65cf`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a6562`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a65cf`
- `ADVAPI32!RegQueryValueExA` at `0x1800a659c`
- `ADVAPI32!RegQueryValueExA` at `0x1800a659c`
- `ADVAPI32!RegCloseKey` at `0x1800a6636`
- `ADVAPI32!RegCloseKey` at `0x1800a6645`
- `ADVAPI32!RegCloseKey` at `0x1800a6636`
- `ADVAPI32!RegCloseKey` at `0x1800a6645`

## pseudocode

```c
__int64 __fastcall VBAddIn::AddInSetRegValue(__int64 a1, int a2)
{
  VBAddInManager *v3; // rcx
  LSTATUS v4; // edi
  CHAR *v5; // rbx
  const CHAR *AddinRegLocation; // rax
  char *v7; // rsi
  int v8; // ebx
  int v9; // eax
  CHAR *v10; // rax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  int v14; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+78h] [rbp+38h] BYREF
  int Data; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v18 = a2;
  v3 = *(VBAddInManager **)(a1 + 144);
  v4 = 0;
  phkResult = 0;
  hKey = 0;
  cbData = 4;
  v5 = 0;
  AddinRegLocation = VBAddInManager::GetAddinRegLocation(v3);
  v7 = (char *)AddinRegLocation;
  if ( AddinRegLocation )
  {
    v8 = lstrlenA(AddinRegLocation);
    v9 = lstrlenA(*(LPCSTR *)(a1 + 72));
    v10 = (CHAR *)malloc(v8 + v9 + 2);
    v5 = v10;
    if ( v10 )
    {
      wsprintfA(v10, "%s\\%s", v7, *(const char **)(a1 + 72));
      v11 = RegOpenKeyExA(*(HKEY *)(a1 + 152), v5, 0, 0x20019u, &hKey);
      v4 = HrFromRegError(v11);
      if ( v4 >= 0 )
      {
        v12 = RegQueryValueExA(hKey, aLoadbehavior_0, 0, 0, (LPBYTE)&Data, &cbData);
        v4 = HrFromRegError(v12);
        if ( Data != v18 )
        {
          v4 = RegOpenKeyExA(*(HKEY *)(a1 + 152), v5, 0, 0xF003Fu, &phkResult);
          if ( v4 >= 0 )
          {
            cbData = 4;
            v13 = RegSetValueExA(phkResult, aLoadbehavior_0, 0, 4u, (const BYTE *)&v18, 4u);
            v14 = HrFromRegError(v13);
            if ( v14 == 70 )
              v14 = -2146768216;
            v4 = v14;
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v7 )
    free(v7);
  if ( v5 )
    free(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a64b8  mov     [rsp-28h+arg_8], edx
0x1800a64bc  push    rbp
0x1800a64bd  push    rbx
0x1800a64be  push    rsi
0x1800a64bf  push    rdi
0x1800a64c0  push    r14
0x1800a64c2  mov     rbp, rsp
0x1800a64c5  mov     eax, 40h
0x1800a64ca  call    _alloca_probe
0x1800a64cf  sub     rsp, rax
0x1800a64d2  mov     r14, rcx
0x1800a64d5  mov     rcx, [rcx+90h]; this
0x1800a64dc  xor     edi, edi
0x1800a64de  and     [rbp+var_10], rdi
0x1800a64e2  and     [rbp+hKey], rdi
0x1800a64e6  mov     [rbp+cbData], 4
0x1800a64ed  xor     ebx, ebx
0x1800a64ef  call    ?GetAddinRegLocation@VBAddInManager@@QEAAPEADXZ; VBAddInManager::GetAddinRegLocation(void)
0x1800a64f4  mov     rsi, rax
0x1800a64f7  test    rax, rax
0x1800a64fa  jz      loc_1800A662D
0x1800a6500  mov     rcx, rax; lpString
0x1800a6503  call    cs:__imp_lstrlenA
0x1800a6509  mov     rcx, [r14+48h]; lpString
0x1800a650d  mov     ebx, eax
0x1800a650f  call    cs:__imp_lstrlenA
0x1800a6515  lea     ecx, [rax+2]
0x1800a6518  add     ecx, ebx
0x1800a651a  movsxd  rcx, ecx; Size
0x1800a651d  call    cs:__imp_malloc
0x1800a6523  mov     rbx, rax
0x1800a6526  test    rax, rax
0x1800a6529  jz      loc_1800A662D
0x1800a652f  mov     r9, [r14+48h]
0x1800a6533  lea     rdx, aSS_1; "%s\\%s"
0x1800a653a  mov     r8, rsi
0x1800a653d  mov     rcx, rax; LPSTR
0x1800a6540  call    cs:__imp_wsprintfA
0x1800a6546  mov     rcx, [r14+98h]; hKey
0x1800a654d  lea     rax, [rbp+hKey]
0x1800a6551  mov     r9d, 20019h; samDesired
0x1800a6557  xor     r8d, r8d; ulOptions
0x1800a655a  mov     rdx, rbx; lpSubKey
0x1800a655d  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a6562  call    cs:__imp_RegOpenKeyExA
0x1800a6568  mov     ecx, eax; int
0x1800a656a  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a656f  mov     edi, eax
0x1800a6571  test    eax, eax
0x1800a6573  js      loc_1800A662D
0x1800a6579  mov     rcx, [rbp+hKey]; hKey
0x1800a657d  lea     rax, [rbp+cbData]
0x1800a6581  lea     rdx, aLoadbehavior_0; "LoadBehavior"
0x1800a6588  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a658d  lea     rax, [rbp+Data]
0x1800a6591  xor     r9d, r9d; lpType
0x1800a6594  xor     r8d, r8d; lpReserved
0x1800a6597  mov     [rsp+40h+phkResult], rax; lpData
0x1800a659c  call    cs:__imp_RegQueryValueExA
0x1800a65a2  mov     ecx, eax; int
0x1800a65a4  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a65a9  mov     edi, eax
0x1800a65ab  mov     eax, [rbp+arg_8]
0x1800a65ae  cmp     [rbp+Data], eax
0x1800a65b1  jz      short loc_1800A662D
0x1800a65b3  mov     rcx, [r14+98h]; hKey
0x1800a65ba  lea     rax, [rbp+var_10]
0x1800a65be  mov     r9d, 0F003Fh; samDesired
0x1800a65c4  xor     r8d, r8d; ulOptions
0x1800a65c7  mov     rdx, rbx; lpSubKey
0x1800a65ca  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a65cf  call    cs:__imp_RegOpenKeyExA
0x1800a65d5  mov     edi, eax
0x1800a65d7  test    eax, eax
0x1800a65d9  jns     short loc_1800A65E7
0x1800a65db  cmp     eax, 46h ; 'F'
0x1800a65de  jnz     short loc_1800A662D
0x1800a65e0  mov     edi, 800AEAA8h
0x1800a65e5  jmp     short loc_1800A662D
0x1800a65e7  mov     rcx, [rbp+var_10]; hKey
0x1800a65eb  lea     rax, [rbp+arg_8]
0x1800a65ef  lea     rdx, aLoadbehavior_0; "LoadBehavior"
0x1800a65f6  mov     r9d, 4; dwType
0x1800a65fc  xor     r8d, r8d; Reserved
0x1800a65ff  mov     dword ptr [rsp+40h+lpcbData], 4; cbData
0x1800a6607  mov     [rsp+40h+phkResult], rax; lpData
0x1800a660c  mov     [rbp+cbData], 4
0x1800a6613  call    cs:__imp_RegSetValueExA
0x1800a6619  mov     ecx, eax; int
0x1800a661b  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a6620  mov     edi, 800AEAA8h
0x1800a6625  cmp     eax, 46h ; 'F'
0x1800a6628  cmovz   eax, edi
0x1800a662b  mov     edi, eax
0x1800a662d  mov     rcx, [rbp+hKey]; hKey
0x1800a6631  test    rcx, rcx
0x1800a6634  jz      short loc_1800A663C
0x1800a6636  call    cs:__imp_RegCloseKey
0x1800a663c  mov     rcx, [rbp+var_10]; hKey
0x1800a6640  test    rcx, rcx
0x1800a6643  jz      short loc_1800A664B
0x1800a6645  call    cs:__imp_RegCloseKey
0x1800a664b  test    rsi, rsi
0x1800a664e  jz      short loc_1800A6659
0x1800a6650  mov     rcx, rsi; Block
0x1800a6653  call    cs:__imp_free
0x1800a6659  test    rbx, rbx
0x1800a665c  jz      short loc_1800A6667
0x1800a665e  mov     rcx, rbx; Block
0x1800a6661  call    cs:__imp_free
0x1800a6667  mov     eax, edi
0x1800a6669  add     rsp, 40h
0x1800a666d  pop     r14
0x1800a666f  pop     rdi
0x1800a6670  pop     rsi
0x1800a6671  pop     rbx
0x1800a6672  pop     rbp
0x1800a6673  retn
```
