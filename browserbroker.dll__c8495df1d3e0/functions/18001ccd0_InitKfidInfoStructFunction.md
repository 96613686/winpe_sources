# InitKfidInfoStructFunction

- ea: `0x18001ccd0`
- end: `0x18001cddc`
- name: `InitKfidInfoStructFunction`
- size: `268`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ccd0`
- `0x18001de18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdb7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001cd27`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001cd27`

## pseudocode

```c
__int64 __fastcall InitKfidInfoStructFunction(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  unsigned int i; // ebx
  unsigned __int64 v4; // rdi
  signed __int64 v5; // rax
  unsigned int v7; // [rsp+28h] [rbp-18h]
  PWSTR ppszPath; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v9; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int64 v10; // [rsp+78h] [rbp+38h] BYREF

  if ( Context )
    *Context = 0;
  for ( i = 0; i < 2; ++i )
  {
    v4 = 544LL * i;
    ppszPath = 0;
    if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)&qword_18003F3B0[v4 / 8], 0x4000u, 0, &ppszPath) >= 0 )
    {
      v9 = 0;
      v10 = 0;
      if ( (int)StringCchCopyExW((unsigned __int16 *)&qword_18003F3B0[v4 / 8 + 2], 0x104u, ppszPath, &v9, &v10, v7) < 0
        || (int)StringCchCopyExW(v9, v10, L"\\", &v9, &v10, v7) < 0 )
      {
        v5 = 0;
        LOWORD(qword_18003F3B0[v4 / 8 + 2]) = 0;
      }
      else
      {
        v5 = ((char *)&v9[v4 / 0xFFFFFFFFFFFFFFFEuLL] - (char *)qword_18003F3B0 - 16) >> 1;
      }
      qword_18003F5C8[68 * i] = v5;
      CoTaskMemFree(ppszPath);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001ccd0  mov     [rsp-18h+arg_0], rbx
0x18001ccd5  mov     [rsp-18h+arg_8], rsi
0x18001ccda  push    rbp
0x18001ccdb  push    rdi
0x18001ccdc  push    r15
0x18001ccde  mov     rbp, rsp
0x18001cce1  sub     rsp, 40h
0x18001cce5  test    r8, r8
0x18001cce8  jz      short loc_18001CCF1
0x18001ccea  mov     qword ptr [r8], 0
0x18001ccf1  xor     ebx, ebx
0x18001ccf3  lea     r15, qword_18003F3B0
0x18001ccfa  cmp     ebx, 2
0x18001ccfd  jnb     loc_18001CDC4
0x18001cd03  mov     eax, ebx
0x18001cd05  lea     r9, [rbp+ppszPath]; ppszPath
0x18001cd09  imul    rdi, rax, 220h
0x18001cd10  xor     r8d, r8d; hToken
0x18001cd13  mov     [rbp+ppszPath], 0
0x18001cd1b  mov     edx, 4000h; dwFlags
0x18001cd20  lea     rsi, [rdi+r15]
0x18001cd24  mov     rcx, rsi; rfid
0x18001cd27  call    cs:__imp_SHGetKnownFolderPath
0x18001cd2d  test    eax, eax
0x18001cd2f  js      loc_18001CDBD
0x18001cd35  mov     r8, [rbp+ppszPath]; unsigned __int16 *
0x18001cd39  lea     rax, [rbp+arg_18]
0x18001cd3d  lea     rcx, [rsi+10h]; unsigned __int16 *
0x18001cd41  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x18001cd46  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x18001cd4a  mov     [rbp+arg_10], 0
0x18001cd52  mov     edx, 104h; unsigned __int64
0x18001cd57  mov     [rbp+arg_18], 0
0x18001cd5f  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001cd64  test    eax, eax
0x18001cd66  js      short loc_18001CDA0
0x18001cd68  mov     rdx, [rbp+arg_18]; unsigned __int64
0x18001cd6c  lea     rax, [rbp+arg_18]
0x18001cd70  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18001cd74  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x18001cd78  lea     r8, SubBlock; "\\"
0x18001cd7f  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x18001cd84  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001cd89  test    eax, eax
0x18001cd8b  js      short loc_18001CDA0
0x18001cd8d  mov     rax, [rbp+arg_10]
0x18001cd91  sub     rax, rdi
0x18001cd94  sub     rax, r15
0x18001cd97  sub     rax, 10h
0x18001cd9b  sar     rax, 1
0x18001cd9e  jmp     short loc_18001CDA8
0x18001cda0  xor     eax, eax
0x18001cda2  mov     [rdi+r15+10h], ax
0x18001cda8  lea     rcx, qword_18003F5C8
0x18001cdaf  mov     [rcx+rdi], rax
0x18001cdb3  mov     rcx, [rbp+ppszPath]; pv
0x18001cdb7  call    cs:__imp_CoTaskMemFree
0x18001cdbd  inc     ebx
0x18001cdbf  jmp     loc_18001CCFA
0x18001cdc4  mov     rbx, [rsp+40h+arg_0]
0x18001cdc9  mov     eax, 1
0x18001cdce  mov     rsi, [rsp+40h+arg_8]
0x18001cdd3  add     rsp, 40h
0x18001cdd7  pop     r15
0x18001cdd9  pop     rdi
0x18001cdda  pop     rbp
0x18001cddb  retn
```
