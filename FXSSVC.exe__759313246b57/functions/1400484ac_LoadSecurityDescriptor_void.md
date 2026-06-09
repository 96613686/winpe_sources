# LoadSecurityDescriptor(void)

- ea: `0x1400484ac`
- end: `0x1400487cb`
- name: `?LoadSecurityDescriptor@@YAKXZ`
- size: `799`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400483d4`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400484ac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140048748`
- `ADVAPI32!RegCloseKey` at `0x140048748`
- `ADVAPI32!RegCreateKeyExW` at `0x14004854a`
- `ADVAPI32!RegCreateKeyExW` at `0x14004854a`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400486d1`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400486d1`
- `ADVAPI32!RegQueryValueExW` at `0x1400485b9`
- `ADVAPI32!RegQueryValueExW` at `0x140048692`
- `ADVAPI32!RegQueryValueExW` at `0x1400485b9`
- `ADVAPI32!RegQueryValueExW` at `0x140048692`
- `KERNEL32!HeapAlloc` at `0x140048626`
- `KERNEL32!HeapAlloc` at `0x140048626`
- `KERNEL32!GetLastError` at `0x140048795`
- `KERNEL32!GetLastError` at `0x140048795`
- `KERNEL32!GetProcessHeap` at `0x14004860d`
- `KERNEL32!GetProcessHeap` at `0x140048759`
- `KERNEL32!GetProcessHeap` at `0x14004860d`
- `KERNEL32!GetProcessHeap` at `0x140048759`
- `KERNEL32!HeapFree` at `0x14004876d`
- `KERNEL32!HeapFree` at `0x14004876d`

## string_xrefs

- `0x140048532`: `Software\Microsoft\Fax\Security`
- `0x1400485b2`: `Descriptor`
- `0x14004868b`: `Descriptor`

## pseudocode

```c
__int64 LoadSecurityDescriptor(void)
{
  BYTE *v0; // rdi
  unsigned int v1; // eax
  unsigned int v2; // ebx
  CMapDeviceId *v3; // rcx
  __int64 v4; // rdx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v7; // r8
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  HANDLE v10; // rax
  DWORD LastError; // eax
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  cbData = 0;
  v0 = 0;
  hKey = 0;
  dwDisposition = 0;
  Type = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Fax\\Security",
         0,
         (LPWSTR)&Class,
         0,
         0x20019u,
         0,
         &hKey,
         &dwDisposition);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 38;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v1);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v1 = RegQueryValueExW(hKey, L"Descriptor", 0, &Type, 0, &cbData);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 39;
      goto LABEL_10;
    }
    goto LABEL_40;
  }
  if ( Type != 3 || !cbData )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v2 = 1009;
    goto LABEL_40;
  }
  v5 = cbData;
  ProcessHeap = GetProcessHeap();
  v7 = v5;
  v2 = 8;
  v0 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( !v0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v9 = 41;
LABEL_23:
    WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    goto LABEL_40;
  }
  v1 = RegQueryValueExW(hKey, L"Descriptor", 0, &Type, v0, &cbData);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 42;
      goto LABEL_10;
    }
    goto LABEL_40;
  }
  if ( IsValidSecurityDescriptor(v0) )
  {
    g_pFaxSD = v0;
    v0 = 0;
    goto LABEL_40;
  }
  v2 = 1338;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 43;
    goto LABEL_23;
  }
LABEL_40:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v0 )
  {
    v10 = GetProcessHeap();
    if ( !HeapFree(v10, 0, v0)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400484ac  push    rbp
0x1400484ae  push    rbx
0x1400484af  push    rdi
0x1400484b0  push    r13
0x1400484b2  push    r15
0x1400484b4  mov     rbp, rsp
0x1400484b7  sub     rsp, 50h
0x1400484bb  mov     [rbp+cbData], 0
0x1400484c2  xor     edi, edi
0x1400484c4  mov     [rbp+hKey], 0
0x1400484cc  mov     [rbp+dwDisposition], 0
0x1400484d3  mov     [rbp+Type], 0
0x1400484da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400484e1  lea     r15, WPP_GLOBAL_Control
0x1400484e8  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400484ef  cmp     rcx, r15
0x1400484f2  jz      short loc_14004850F
0x1400484f4  test    byte ptr [rcx+1Ch], 4
0x1400484f8  jz      short loc_14004850F
0x1400484fa  cmp     byte ptr [rcx+19h], 5
0x1400484fe  jb      short loc_14004850F
0x140048500  mov     rcx, [rcx+10h]
0x140048504  lea     edx, [rdi+25h]
0x140048507  mov     r8, r13
0x14004850a  call    WPP_SF_
0x14004850f  lea     rax, [rbp+dwDisposition]
0x140048513  xor     r8d, r8d; Reserved
0x140048516  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x14004851b  lea     r9, Class; lpClass
0x140048522  lea     rax, [rbp+hKey]
0x140048526  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004852d  mov     [rsp+50h+phkResult], rax; phkResult
0x140048532  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Fax\\Security"
0x140048539  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14004853e  mov     [rsp+50h+samDesired], 20019h; samDesired
0x140048546  mov     [rsp+50h+dwOptions], edi; dwOptions
0x14004854a  call    cs:__imp_RegCreateKeyExW
0x140048551  nop     dword ptr [rax+rax+00h]
0x140048556  mov     ebx, eax
0x140048558  test    eax, eax
0x14004855a  jz      short loc_140048599
0x14004855c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048563  cmp     rcx, r15
0x140048566  jz      loc_14004873F
0x14004856c  test    byte ptr [rcx+1Ch], 4
0x140048570  jz      loc_14004873F
0x140048576  cmp     byte ptr [rcx+19h], 2
0x14004857a  jb      loc_14004873F
0x140048580  mov     edx, 26h ; '&'
0x140048585  mov     rcx, [rcx+10h]
0x140048589  mov     r9d, eax
0x14004858c  mov     r8, r13
0x14004858f  call    WPP_SF_d
0x140048594  jmp     loc_14004873F
0x140048599  mov     rcx, [rbp+hKey]; hKey
0x14004859d  lea     rax, [rbp+cbData]
0x1400485a1  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x1400485a6  lea     r9, [rbp+Type]; lpType
0x1400485aa  xor     r8d, r8d; lpReserved
0x1400485ad  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x1400485b2  lea     rdx, aDescriptor; "Descriptor"
0x1400485b9  call    cs:__imp_RegQueryValueExW
0x1400485c0  nop     dword ptr [rax+rax+00h]
0x1400485c5  mov     ebx, eax
0x1400485c7  test    eax, eax
0x1400485c9  jz      short loc_1400485F6
0x1400485cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400485d2  cmp     rcx, r15
0x1400485d5  jz      loc_14004873F
0x1400485db  test    byte ptr [rcx+1Ch], 4
0x1400485df  jz      loc_14004873F
0x1400485e5  cmp     byte ptr [rcx+19h], 2
0x1400485e9  jb      loc_14004873F
0x1400485ef  mov     edx, 27h ; '''
0x1400485f4  jmp     short loc_140048585
0x1400485f6  cmp     [rbp+Type], 3
0x1400485fa  jnz     loc_140048711
0x140048600  mov     eax, [rbp+cbData]
0x140048603  test    eax, eax
0x140048605  jz      loc_140048711
0x14004860b  mov     ebx, eax
0x14004860d  call    cs:__imp_GetProcessHeap
0x140048614  nop     dword ptr [rax+rax+00h]
0x140048619  mov     r8d, ebx; dwBytes
0x14004861c  mov     ebx, 8
0x140048621  mov     edx, ebx; dwFlags
0x140048623  mov     rcx, rax; hHeap
0x140048626  call    cs:__imp_HeapAlloc
0x14004862d  nop     dword ptr [rax+rax+00h]
0x140048632  mov     rdi, rax
0x140048635  test    rax, rax
0x140048638  jnz     short loc_140048672
0x14004863a  mov     rcx, cs:WPP_GLOBAL_Control
0x140048641  cmp     rcx, r15
0x140048644  jz      loc_14004873F
0x14004864a  test    byte ptr [rcx+1Ch], 4
0x14004864e  jz      loc_14004873F
0x140048654  cmp     byte ptr [rcx+19h], 2
0x140048658  jb      loc_14004873F
0x14004865e  lea     edx, [rbx+21h]
0x140048661  mov     rcx, [rcx+10h]
0x140048665  mov     r8, r13
0x140048668  call    WPP_SF_
0x14004866d  jmp     loc_14004873F
0x140048672  mov     rcx, [rbp+hKey]; hKey
0x140048676  lea     rax, [rbp+cbData]
0x14004867a  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x14004867f  lea     r9, [rbp+Type]; lpType
0x140048683  xor     r8d, r8d; lpReserved
0x140048686  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x14004868b  lea     rdx, aDescriptor; "Descriptor"
0x140048692  call    cs:__imp_RegQueryValueExW
0x140048699  nop     dword ptr [rax+rax+00h]
0x14004869e  mov     ebx, eax
0x1400486a0  test    eax, eax
0x1400486a2  jz      short loc_1400486CE
0x1400486a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400486ab  cmp     rcx, r15
0x1400486ae  jz      loc_14004873F
0x1400486b4  test    byte ptr [rcx+1Ch], 4
0x1400486b8  jz      loc_14004873F
0x1400486be  cmp     byte ptr [rcx+19h], 2
0x1400486c2  jb      short loc_14004873F
0x1400486c4  mov     edx, 2Ah ; '*'
0x1400486c9  jmp     loc_140048585
0x1400486ce  mov     rcx, rdi; pSecurityDescriptor
0x1400486d1  call    cs:__imp_IsValidSecurityDescriptor
0x1400486d8  nop     dword ptr [rax+rax+00h]
0x1400486dd  test    eax, eax
0x1400486df  jnz     short loc_140048706
0x1400486e1  mov     ebx, 53Ah
0x1400486e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400486ed  cmp     rcx, r15
0x1400486f0  jz      short loc_14004873F
0x1400486f2  test    byte ptr [rcx+1Ch], 4
0x1400486f6  jz      short loc_14004873F
0x1400486f8  cmp     byte ptr [rcx+19h], 2
0x1400486fc  jb      short loc_14004873F
0x1400486fe  lea     edx, [rax+2Bh]
0x140048701  jmp     loc_140048661
0x140048706  mov     cs:?g_pFaxSD@@3PEAXEA, rdi; void * g_pFaxSD
0x14004870d  xor     edi, edi
0x14004870f  jmp     short loc_14004873F
0x140048711  mov     rcx, cs:WPP_GLOBAL_Control
0x140048718  cmp     rcx, r15
0x14004871b  jz      short loc_14004873A
0x14004871d  test    byte ptr [rcx+1Ch], 4
0x140048721  jz      short loc_14004873A
0x140048723  cmp     byte ptr [rcx+19h], 2
0x140048727  jb      short loc_14004873A
0x140048729  mov     rcx, [rcx+10h]
0x14004872d  mov     edx, 28h ; '('
0x140048732  mov     r8, r13
0x140048735  call    WPP_SF_
0x14004873a  mov     ebx, 3F1h
0x14004873f  mov     rcx, [rbp+hKey]; hKey
0x140048743  test    rcx, rcx
0x140048746  jz      short loc_140048754
0x140048748  call    cs:__imp_RegCloseKey
0x14004874f  nop     dword ptr [rax+rax+00h]
0x140048754  test    rdi, rdi
0x140048757  jz      short loc_1400487BC
0x140048759  call    cs:__imp_GetProcessHeap
0x140048760  nop     dword ptr [rax+rax+00h]
0x140048765  mov     r8, rdi; lpMem
0x140048768  xor     edx, edx; dwFlags
0x14004876a  mov     rcx, rax; hHeap
0x14004876d  call    cs:__imp_HeapFree
0x140048774  nop     dword ptr [rax+rax+00h]
0x140048779  test    eax, eax
0x14004877b  jnz     short loc_1400487BC
0x14004877d  mov     rax, cs:WPP_GLOBAL_Control
0x140048784  cmp     rax, r15
0x140048787  jz      short loc_1400487BC
0x140048789  test    byte ptr [rax+1Ch], 4
0x14004878d  jz      short loc_1400487BC
0x14004878f  cmp     byte ptr [rax+19h], 2
0x140048793  jb      short loc_1400487BC
0x140048795  call    cs:__imp_GetLastError
0x14004879c  nop     dword ptr [rax+rax+00h]
0x1400487a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487a8  mov     edx, 2Ch ; ','
0x1400487ad  mov     r9d, eax
0x1400487b0  mov     r8, r13
0x1400487b3  mov     rcx, [rcx+10h]
0x1400487b7  call    WPP_SF_d
0x1400487bc  mov     eax, ebx
0x1400487be  add     rsp, 50h
0x1400487c2  pop     r15
0x1400487c4  pop     r13
0x1400487c6  pop     rdi
0x1400487c7  pop     rbx
0x1400487c8  pop     rbp
0x1400487c9  retn
```
