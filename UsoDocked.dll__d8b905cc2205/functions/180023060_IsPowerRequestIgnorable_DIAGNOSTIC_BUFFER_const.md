# IsPowerRequestIgnorable(_DIAGNOSTIC_BUFFER const &)

- ea: `0x180023060`
- end: `0x18002319b`
- name: `?IsPowerRequestIgnorable@@YA_NAEBU_DIAGNOSTIC_BUFFER@@@Z`
- size: `315`
- prototype: `bool __fastcall(const struct _DIAGNOSTIC_BUFFER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800227c0`
- `0x180022f60`

## callees

- `0x180023060`
- `0x1800231a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023120`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002314f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023172`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023120`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002314f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023172`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180023099`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180023099`

## string_xrefs

- `0x180023162`: `srvsvc.dll`

## pseudocode

```c
char __fastcall IsPowerRequestIgnorable(const struct _DIAGNOSTIC_BUFFER *a1)
{
  __int64 v1; // rax
  char *v4; // rbx
  __int64 v5; // rax
  LPWSTR FileNameW; // rbp
  char v7; // si
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rdx
  int v10; // ecx
  int v11; // ecx
  const wchar_t *v12; // rdx
  const wchar_t **i; // rbx
  __int64 v14; // r8
  __int16 v15; // bx
  const wchar_t *v16; // [rsp+20h] [rbp-28h] BYREF
  char v17; // [rsp+28h] [rbp-20h] BYREF

  v1 = *((_QWORD *)a1 + 4);
  if ( !v1 )
    return 0;
  v4 = (char *)a1 + v1;
  v5 = *(_QWORD *)((char *)a1 + v1 + 8);
  if ( v5 )
    FileNameW = PathFindFileNameW((LPCWSTR)&v4[v5]);
  else
    FileNameW = (LPWSTR)&psz;
  v7 = 1;
  if ( (*v4 & 1) != 0 )
  {
    v8 = *((_QWORD *)v4 + 1);
LABEL_11:
    v9 = (const unsigned __int16 *)&v4[v8];
    goto LABEL_13;
  }
  if ( (*v4 & 2) != 0 && *((_DWORD *)v4 + 5) )
  {
    v8 = *((_QWORD *)v4 + 3);
    goto LABEL_11;
  }
  v9 = 0;
LABEL_13:
  v10 = *((_DWORD *)a1 + 2);
  if ( !v10 )
  {
    if ( !v9 || (unsigned int)_o__wcsnicmp(L"Sleep Idle State Disabled", v9, 25) )
    {
      if ( (*v4 & 2) == 0 )
        return 0;
      v15 = *((_WORD *)v4 + 8);
      if ( (unsigned int)_o__wcsnicmp(FileNameW, L"srvsvc.dll", 10) || v15 != 107 )
        return 0;
    }
    return v7;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( *((_QWORD *)a1 + 2) )
    {
      v12 = L"LockScreenContentServer.exe";
      v16 = L"LockScreenContentServer.exe";
      for ( i = &v16; ; v12 = *i )
      {
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        if ( !(unsigned int)_o__wcsnicmp(FileNameW, v12, v14) )
          break;
        if ( ++i == (const wchar_t **)&v17 )
          return 0;
      }
    }
    return v7;
  }
  if ( v11 != 1 )
    return 0;
  return IsServiceIgnorable(*((_DWORD *)a1 + 6), *((_DWORD *)a1 + 7), v9);
}

```

## disassembly

```asm
0x180023060  mov     [rsp+arg_8], rbx
0x180023065  mov     [rsp+arg_10], rbp
0x18002306a  push    rsi
0x18002306b  push    rdi
0x18002306c  push    r14
0x18002306e  sub     rsp, 30h
0x180023072  mov     rax, [rcx+20h]
0x180023076  xor     r14d, r14d
0x180023079  mov     rdi, rcx
0x18002307c  test    rax, rax
0x18002307f  jnz     short loc_180023088
0x180023081  xor     al, al
0x180023083  jmp     loc_180023188
0x180023088  lea     rbx, [rax+rcx]
0x18002308c  mov     rax, [rbx+8]
0x180023090  test    rax, rax
0x180023093  jz      short loc_1800230A4
0x180023095  lea     rcx, [rax+rbx]; pszPath
0x180023099  call    cs:__imp_PathFindFileNameW
0x18002309f  mov     rbp, rax
0x1800230a2  jmp     short loc_1800230AB
0x1800230a4  lea     rbp, psz
0x1800230ab  mov     sil, 1
0x1800230ae  test    [rbx], sil
0x1800230b1  jz      short loc_1800230B9
0x1800230b3  mov     rdx, [rbx+8]
0x1800230b7  jmp     short loc_1800230C8
0x1800230b9  test    byte ptr [rbx], 2
0x1800230bc  jz      short loc_1800230CD
0x1800230be  cmp     [rbx+14h], r14d
0x1800230c2  jbe     short loc_1800230CD
0x1800230c4  mov     rdx, [rbx+18h]
0x1800230c8  add     rdx, rbx
0x1800230cb  jmp     short loc_1800230D0
0x1800230cd  mov     rdx, r14
0x1800230d0  mov     ecx, [rdi+8]
0x1800230d3  test    ecx, ecx
0x1800230d5  jz      short loc_18002313D
0x1800230d7  sub     ecx, 1
0x1800230da  jz      short loc_1800230F4
0x1800230dc  cmp     ecx, 1
0x1800230df  jnz     short loc_180023081
0x1800230e1  mov     ecx, [rdi+18h]; unsigned int
0x1800230e4  mov     r8, rdx; unsigned __int16 *
0x1800230e7  mov     edx, [rdi+1Ch]; unsigned int
0x1800230ea  call    ?IsServiceIgnorable@@YA_NKKPEBG@Z; IsServiceIgnorable(ulong,ulong,ushort const *)
0x1800230ef  jmp     loc_180023188
0x1800230f4  cmp     [rdi+10h], r14
0x1800230f8  jz      loc_180023185
0x1800230fe  lea     rdx, aLockscreencont; "LockScreenContentServer.exe"
0x180023105  mov     [rsp+48h+var_28], rdx
0x18002310a  lea     rbx, [rsp+48h+var_28]
0x18002310f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023113  inc     r8
0x180023116  cmp     [rdx+r8*2], r14w
0x18002311b  jnz     short loc_180023113
0x18002311d  mov     rcx, rbp
0x180023120  call    cs:__imp__o__wcsnicmp
0x180023126  test    eax, eax
0x180023128  jz      short loc_180023185
0x18002312a  add     rbx, 8
0x18002312e  lea     rax, [rsp+48h+var_20]
0x180023133  cmp     rbx, rax
0x180023136  jz      short loc_180023182
0x180023138  mov     rdx, [rbx]
0x18002313b  jmp     short loc_18002310F
0x18002313d  test    rdx, rdx
0x180023140  jz      short loc_180023159
0x180023142  mov     r8d, 19h
0x180023148  lea     rcx, aSleepIdleState; "Sleep Idle State Disabled"
0x18002314f  call    cs:__imp__o__wcsnicmp
0x180023155  test    eax, eax
0x180023157  jz      short loc_180023185
0x180023159  test    byte ptr [rbx], 2
0x18002315c  jz      short loc_180023182
0x18002315e  movzx   ebx, word ptr [rbx+10h]
0x180023162  lea     rdx, aSrvsvcDll; "srvsvc.dll"
0x180023169  mov     r8d, 0Ah
0x18002316f  mov     rcx, rbp
0x180023172  call    cs:__imp__o__wcsnicmp
0x180023178  test    eax, eax
0x18002317a  jnz     short loc_180023182
0x18002317c  cmp     bx, 6Bh ; 'k'
0x180023180  jz      short loc_180023185
0x180023182  mov     sil, r14b
0x180023185  mov     al, sil
0x180023188  mov     rbx, [rsp+48h+arg_8]
0x18002318d  mov     rbp, [rsp+48h+arg_10]
0x180023192  add     rsp, 30h
0x180023196  pop     r14
0x180023198  pop     rdi
0x180023199  pop     rsi
0x18002319a  retn
```
