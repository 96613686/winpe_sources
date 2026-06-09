# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x180003c10`
- end: `0x180003d16`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `262`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180002860`
- `0x1800040b0`

## callees

- `0x180003c10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d06`

## pseudocode

```c
void __fastcall FreeRepairInfos(struct tagRepairInfo *pv, unsigned int a2, int a3)
{
  unsigned int v6; // edi
  __int64 v7; // rsi
  __int64 v8; // rbx
  LPWSTR pwszDescription; // rcx
  UiInfo *p_UiInfo; // rbx
  UI_INFO_TYPE type; // eax
  LPWSTR pwszFile; // rcx
  LPWSTR pwzNull; // rcx
  LPWSTR pwszParameters; // rcx

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      v8 = v7;
      CoTaskMemFree(pv[v7].pwszClassName);
      pwszDescription = pv[v7].pwszDescription;
      pv[v8].pwszClassName = 0;
      CoTaskMemFree(pwszDescription);
      pv[v8].pwszDescription = 0;
      p_UiInfo = &pv[v7].UiInfo;
      if ( p_UiInfo )
      {
        type = p_UiInfo->type;
        if ( p_UiInfo->type == UIT_SHELL_COMMAND )
        {
          CoTaskMemFree(p_UiInfo->ShellInfo.pwszDirectory);
          pwszFile = p_UiInfo->ShellInfo.pwszFile;
          p_UiInfo->ShellInfo.pwszDirectory = 0;
          CoTaskMemFree(pwszFile);
          pwzNull = p_UiInfo->pwzNull;
          p_UiInfo->ShellInfo.pwszFile = 0;
          CoTaskMemFree(pwzNull);
          pwszParameters = p_UiInfo->ShellInfo.pwszParameters;
          p_UiInfo->pwzNull = 0;
          CoTaskMemFree(pwszParameters);
          p_UiInfo->ShellInfo.pwszParameters = 0;
        }
        else if ( type == UIT_HELP_PANE || type == UIT_DUI )
        {
          CoTaskMemFree(p_UiInfo->pwzNull);
          p_UiInfo->pwzNull = 0;
        }
        p_UiInfo->type = UIT_NONE;
      }
      ++v6;
      ++v7;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180003c10  test    rcx, rcx
0x180003c13  jz      locret_180003D15
0x180003c19  push    rbp
0x180003c1a  push    r14
0x180003c1c  push    r15
0x180003c1e  sub     rsp, 20h
0x180003c22  mov     r15d, r8d
0x180003c25  mov     r14d, edx
0x180003c28  mov     rbp, rcx
0x180003c2b  test    edx, edx
0x180003c2d  jz      loc_180003D0C
0x180003c33  mov     [rsp+38h+arg_0], rbx
0x180003c38  mov     [rsp+38h+arg_8], rsi
0x180003c3d  mov     [rsp+38h+arg_10], rdi
0x180003c42  mov     [rsp+38h+arg_18], r12
0x180003c47  xor     r12d, r12d
0x180003c4a  mov     edi, r12d
0x180003c4d  mov     esi, r12d
0x180003c50  imul    rbx, rsi, 70h ; 'p'
0x180003c54  mov     rcx, [rbx+rbp+10h]; pv
0x180003c59  call    cs:__imp_CoTaskMemFree
0x180003c5f  mov     rcx, [rbx+rbp+18h]; pv
0x180003c64  mov     [rbx+rbp+10h], r12
0x180003c69  call    cs:__imp_CoTaskMemFree
0x180003c6f  mov     [rbx+rbp+18h], r12
0x180003c74  add     rbx, 38h ; '8'
0x180003c78  add     rbx, rbp
0x180003c7b  jz      short loc_180003CDC
0x180003c7d  mov     eax, [rbx]
0x180003c7f  cmp     eax, 2
0x180003c82  jnz     short loc_180003CBE
0x180003c84  mov     rcx, [rbx+20h]; pv
0x180003c88  call    cs:__imp_CoTaskMemFree
0x180003c8e  mov     rcx, [rbx+10h]; pv
0x180003c92  mov     [rbx+20h], r12
0x180003c96  call    cs:__imp_CoTaskMemFree
0x180003c9c  mov     rcx, [rbx+8]; pv
0x180003ca0  mov     [rbx+10h], r12
0x180003ca4  call    cs:__imp_CoTaskMemFree
0x180003caa  mov     rcx, [rbx+18h]; pv
0x180003cae  mov     [rbx+8], r12
0x180003cb2  call    cs:__imp_CoTaskMemFree
0x180003cb8  mov     [rbx+18h], r12
0x180003cbc  jmp     short loc_180003CD6
0x180003cbe  cmp     eax, 3
0x180003cc1  jz      short loc_180003CC8
0x180003cc3  cmp     eax, 4
0x180003cc6  jnz     short loc_180003CD6
0x180003cc8  mov     rcx, [rbx+8]; pv
0x180003ccc  call    cs:__imp_CoTaskMemFree
0x180003cd2  mov     [rbx+8], r12
0x180003cd6  mov     dword ptr [rbx], 1
0x180003cdc  inc     edi
0x180003cde  inc     rsi
0x180003ce1  cmp     edi, r14d
0x180003ce4  jb      loc_180003C50
0x180003cea  mov     r12, [rsp+38h+arg_18]
0x180003cef  mov     rdi, [rsp+38h+arg_10]
0x180003cf4  mov     rsi, [rsp+38h+arg_8]
0x180003cf9  mov     rbx, [rsp+38h+arg_0]
0x180003cfe  test    r15d, r15d
0x180003d01  jz      short loc_180003D0C
0x180003d03  mov     rcx, rbp; pv
0x180003d06  call    cs:__imp_CoTaskMemFree
0x180003d0c  add     rsp, 20h
0x180003d10  pop     r15
0x180003d12  pop     r14
0x180003d14  pop     rbp
0x180003d15  retn
```
