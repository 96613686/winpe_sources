# RegGetValIfExist(HKEY__ *,ushort *,ushort *,ulong,ushort *)

- ea: `0x1800197f8`
- end: `0x180019915`
- name: `?RegGetValIfExist@@YAJPEAUHKEY__@@PEAG1K1@Z`
- size: `285`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, BYTE *lpData@<r8>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012acc`

## callees

- `0x1800197f8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800198f5`
- `ADVAPI32!RegSetValueExW` at `0x1800198f5`
- `ADVAPI32!RegQueryValueExW` at `0x180019854`
- `ADVAPI32!RegQueryValueExW` at `0x180019854`

## pseudocode

```c
LSTATUS __fastcall RegGetValIfExist(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData, DWORD a4, BYTE *a5)
{
  LSTATUS result; // eax
  BYTE *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r8
  LPCWSTR v12; // rcx
  BYTE *v13; // rcx
  __int64 v14; // rcx
  BYTE *v15; // rax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  cbData = a4;
  if ( !hKey )
    return 110;
  v9 = a5;
  cbData = 520;
  Type = 1;
  result = RegQueryValueExW(hKey, lpValueName, 0, &Type, a5, &cbData);
  if ( result )
  {
    v10 = 2147483646;
    v11 = 260;
    v12 = lpValueName;
    do
    {
      if ( !v10 )
        break;
      if ( !*v12 )
        break;
      *(_WORD *)v9 = *v12++;
      v9 += 2;
      --v10;
      --v11;
    }
    while ( v11 );
    v13 = v9 - 2;
    if ( v11 )
      v13 = v9;
    *(_WORD *)v13 = 0;
    if ( !v11 || !lpData )
      return 87;
    v14 = 260;
    v15 = lpData;
    do
    {
      if ( !*(_WORD *)v15 )
        break;
      v15 += 2;
      --v14;
    }
    while ( v14 );
    if ( v14 )
      return RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * (v14 != 0 ? 260 - v14 : 0) + 2);
    else
      return 87;
  }
  return result;
}

```

## disassembly

```asm
0x1800197f8  mov     [rsp+arg_8], rbx
0x1800197fd  mov     [rsp+arg_10], rbp
0x180019802  mov     [rsp+cbData], r9d
0x180019807  push    rsi
0x180019808  push    rdi
0x180019809  push    r14
0x18001980b  sub     rsp, 30h
0x18001980f  xor     r14d, r14d
0x180019812  mov     rdi, r8
0x180019815  mov     rbp, rdx
0x180019818  mov     rsi, rcx
0x18001981b  test    rcx, rcx
0x18001981e  jnz     short loc_180019828
0x180019820  lea     eax, [rcx+6Eh]
0x180019823  jmp     loc_180019902
0x180019828  mov     rbx, [rsp+48h+arg_20]
0x18001982d  lea     rax, [rsp+48h+cbData]
0x180019832  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180019837  lea     r9, [rsp+48h+Type]; lpType
0x18001983c  xor     r8d, r8d; lpReserved
0x18001983f  mov     [rsp+48h+lpData], rbx; lpData
0x180019844  mov     [rsp+48h+cbData], 208h
0x18001984c  mov     [rsp+48h+Type], 1
0x180019854  call    cs:__imp_RegQueryValueExW
0x18001985a  test    eax, eax
0x18001985c  jz      loc_180019902
0x180019862  mov     edx, 104h
0x180019867  mov     eax, 7FFFFFFEh
0x18001986c  mov     r8d, edx
0x18001986f  mov     rcx, rbp
0x180019872  test    rax, rax
0x180019875  jz      short loc_180019896
0x180019877  movzx   r9d, word ptr [rcx]
0x18001987b  test    r9w, r9w
0x18001987f  jz      short loc_180019896
0x180019881  mov     [rbx], r9w
0x180019885  add     rcx, 2
0x180019889  add     rbx, 2
0x18001988d  dec     rax
0x180019890  sub     r8, 1
0x180019894  jnz     short loc_180019872
0x180019896  test    r8, r8
0x180019899  lea     rcx, [rbx-2]
0x18001989d  cmovnz  rcx, rbx
0x1800198a1  mov     [rcx], r14w
0x1800198a5  jz      short loc_1800198FD
0x1800198a7  test    rdi, rdi
0x1800198aa  jz      short loc_1800198FD
0x1800198ac  mov     rcx, rdx
0x1800198af  mov     rax, rdi
0x1800198b2  cmp     [rax], r14w
0x1800198b6  jz      short loc_1800198C2
0x1800198b8  add     rax, 2
0x1800198bc  sub     rcx, 1
0x1800198c0  jnz     short loc_1800198B2
0x1800198c2  sub     rdx, rcx
0x1800198c5  mov     rax, rcx
0x1800198c8  neg     rax
0x1800198cb  sbb     rax, rax
0x1800198ce  and     rax, rdx
0x1800198d1  test    rcx, rcx
0x1800198d4  jz      short loc_1800198FD
0x1800198d6  lea     eax, ds:2[rax*2]
0x1800198dd  mov     r9d, 1; dwType
0x1800198e3  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x1800198e7  xor     r8d, r8d; Reserved
0x1800198ea  mov     rdx, rbp; lpValueName
0x1800198ed  mov     [rsp+48h+lpData], rdi; lpData
0x1800198f2  mov     rcx, rsi; hKey
0x1800198f5  call    cs:__imp_RegSetValueExW
0x1800198fb  jmp     short loc_180019902
0x1800198fd  mov     eax, 57h ; 'W'
0x180019902  mov     rbx, [rsp+48h+arg_8]
0x180019907  mov     rbp, [rsp+48h+arg_10]
0x18001990c  add     rsp, 30h
0x180019910  pop     r14
0x180019912  pop     rdi
0x180019913  pop     rsi
0x180019914  retn
```
