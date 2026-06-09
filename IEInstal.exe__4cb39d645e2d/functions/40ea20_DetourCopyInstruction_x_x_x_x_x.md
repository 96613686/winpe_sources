# DetourCopyInstruction(x,x,x,x,x)

- ea: `0x40ea20`
- end: `0x40eaff`
- name: `_DetourCopyInstruction@20`
- size: `223`
- prototype: `int __stdcall(char *, int, unsigned __int8 *, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x40d860`

## callees

- `0x40cb60`
- `0x40d1d0`
- `0x40ea20`

## import_xrefs

- `KERNEL32!SetLastError` at `0x40eaa8`
- `KERNEL32!SetLastError` at `0x40eaa8`

## pseudocode

```c
int __stdcall DetourCopyInstruction(char *a1, int a2, unsigned __int8 *a3, char *a4, char *a5)
{
  char *v5; // edx
  char *v6; // ecx
  char *v8; // eax
  _DWORD v9[8]; // [esp+0h] [ebp-70h] BYREF
  char *v10; // [esp+20h] [ebp-50h]
  char v11; // [esp+24h] [ebp-4Ch] BYREF
  char v12; // [esp+28h] [ebp-48h] BYREF
  char v13; // [esp+2Ch] [ebp-44h] BYREF

  v5 = &v12;
  v9[0] = 0;
  v6 = &v11;
  v9[1] = 0;
  if ( a4 )
    v5 = a4;
  v9[2] = 0;
  v9[4] = 0;
  if ( a5 )
    v6 = a5;
  v9[5] = 0;
  v10 = v6;
  v9[3] = 0;
  v9[7] = v5;
  *(_DWORD *)v5 = 0;
  *(_DWORD *)v10 = 0;
  if ( a3 )
  {
    v8 = &v13;
    if ( a1 )
      v8 = a1;
    return (*((int (__thiscall **)(_DWORD *, const struct CDetourDis::COPYENTRY *const *, char *, unsigned __int8 *))&CDetourDis::s_rceCopyTable
            + 2 * *a3
            + 1))(
             v9,
             &CDetourDis::s_rceCopyTable + 2 * *a3,
             v8,
             a3);
  }
  else
  {
    SetLastError(0xDu);
    return 0;
  }
}

```

## disassembly

```asm
0x40ea20  sub     esp, 70h
0x40ea23  mov     eax, ___security_cookie
0x40ea28  xor     eax, esp
0x40ea2a  mov     [esp+70h+var_4], eax
0x40ea2e  mov     eax, [esp+70h+arg_C]
0x40ea35  lea     edx, [esp+70h+var_48]
0x40ea39  test    eax, eax
0x40ea3b  mov     [esp+70h+var_70], 0
0x40ea42  lea     ecx, [esp+70h+var_4C]
0x40ea46  mov     [esp+70h+var_6C], 0
0x40ea4e  cmovnz  edx, eax
0x40ea51  mov     [esp+70h+var_68], 0
0x40ea59  mov     eax, [esp+70h+arg_10]
0x40ea60  test    eax, eax
0x40ea62  mov     [esp+70h+var_60], 0
0x40ea6a  cmovnz  ecx, eax
0x40ea6d  mov     [esp+70h+var_5C], 0
0x40ea75  mov     [esp+70h+var_50], ecx
0x40ea79  mov     [esp+70h+var_64], 0
0x40ea81  mov     [esp+70h+var_54], edx
0x40ea85  mov     dword ptr [edx], 0
0x40ea8b  mov     eax, [esp+70h+var_50]
0x40ea8f  push    ebx
0x40ea90  mov     ebx, [esp+74h+arg_0]
0x40ea94  push    edi
0x40ea95  mov     edi, [esp+78h+arg_8]
0x40ea9c  mov     dword ptr [eax], 0
0x40eaa2  test    edi, edi
0x40eaa4  jnz     short loc_40EAC3
0x40eaa6  push    0Dh; dwErrCode
0x40eaa8  call    ds:__imp__SetLastError@4; SetLastError(x)
0x40eaae  pop     edi
0x40eaaf  xor     eax, eax
0x40eab1  pop     ebx
0x40eab2  mov     ecx, [esp+70h+var_4]
0x40eab6  xor     ecx, esp; StackCookie
0x40eab8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40eabd  add     esp, 70h
0x40eac0  retn    14h
0x40eac3  movzx   eax, byte ptr [edi]
0x40eac6  test    ebx, ebx
0x40eac8  push    esi
0x40eac9  push    edi
0x40eaca  lea     esi, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B[eax*8]; CDetourDis::COPYENTRY const * const CDetourDis::s_rceCopyTable
0x40ead1  lea     eax, [esp+80h+var_44]
0x40ead5  cmovnz  eax, ebx
0x40ead8  push    eax
0x40ead9  push    esi
0x40eada  mov     esi, [esi+4]
0x40eadd  mov     ecx, esi
0x40eadf  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40eae5  lea     ecx, [esp+88h+var_70]
0x40eae9  call    esi
0x40eaeb  mov     ecx, [esp+7Ch+var_4]
0x40eaef  pop     esi
0x40eaf0  pop     edi
0x40eaf1  pop     ebx
0x40eaf2  xor     ecx, esp; StackCookie
0x40eaf4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40eaf9  add     esp, 70h
0x40eafc  retn    14h
```
