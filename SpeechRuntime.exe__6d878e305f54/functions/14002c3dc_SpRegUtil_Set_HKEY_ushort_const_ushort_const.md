# SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *)

- ea: `0x14002c3dc`
- end: `0x14002c45a`
- name: `?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG1@Z`
- size: `126`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14002c320`

## callees

- `0x140022fa8`
- `0x14002c3dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14002c43c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14002c43c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002c414`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002c414`

## string_xrefs

- `0x14002c3fb`: `AgentActivationDefaultApp`

## pseudocode

```c
int __fastcall SpRegUtil::Set(HKEY hKey, const unsigned __int16 *a2, const BYTE *a3)
{
  __int64 v3; // rax
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a3[2 * v3] );
  v5 = RegSetValueExW(hKey, L"AgentActivationDefaultApp", 0, 2u, a3, 2 * v3);
  if ( v5 )
  {
    v6 = 267;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
             (const char *)v5,
             lpData);
  }
  v5 = RegFlushKey(hKey);
  if ( v5 )
  {
    v6 = 268;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
             (const char *)v5,
             lpData);
  }
  return 0;
}

```

## disassembly

```asm
0x14002c3dc  mov     [rsp+arg_0], rbx
0x14002c3e1  push    rdi
0x14002c3e2  sub     rsp, 30h
0x14002c3e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002c3ea  mov     rbx, rcx
0x14002c3ed  xor     edi, edi
0x14002c3ef  inc     rax
0x14002c3f2  cmp     [r8+rax*2], di
0x14002c3f7  jnz     short loc_14002C3EF
0x14002c3f9  add     eax, eax
0x14002c3fb  lea     rdx, aAgentactivatio_2; "AgentActivationDefaultApp"
0x14002c402  mov     [rsp+38h+cbData], eax; cbData
0x14002c406  mov     r9d, 2; dwType
0x14002c40c  mov     [rsp+38h+lpData], r8; unsigned int
0x14002c411  xor     r8d, r8d; Reserved
0x14002c414  call    cs:__imp_RegSetValueExW
0x14002c41a  test    eax, eax
0x14002c41c  jz      short loc_14002C439
0x14002c41e  mov     edx, 10Bh; void *
0x14002c423  mov     rcx, [rsp+38h]; this
0x14002c428  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\enduser\\inc\\sap"...
0x14002c42f  mov     r9d, eax; char *
0x14002c432  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14002c437  jmp     short loc_14002C44F
0x14002c439  mov     rcx, rbx; hKey
0x14002c43c  call    cs:__imp_RegFlushKey
0x14002c442  test    eax, eax
0x14002c444  jz      short loc_14002C44D
0x14002c446  mov     edx, 10Ch
0x14002c44b  jmp     short loc_14002C423
0x14002c44d  xor     eax, eax
0x14002c44f  mov     rbx, [rsp+38h+arg_0]
0x14002c454  add     rsp, 30h
0x14002c458  pop     rdi
0x14002c459  retn
```
