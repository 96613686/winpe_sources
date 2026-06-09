# WwanProfileGetRootPath

- ea: `0x18000e0e0`
- end: `0x18000e1af`
- name: `WwanProfileGetRootPath`
- size: `207`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e050`

## callees

- `0x180008458`
- `0x18000e0e0`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000e12b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000e12b`

## pseudocode

```c
__int64 __fastcall WwanProfileGetRootPath(unsigned __int16 *a1, unsigned __int64 a2, int a3)
{
  int BasicProfileFolderPath; // eax
  unsigned int v8; // ecx
  const wchar_t *v9; // rax
  int v10; // eax

  *a1 = 0;
  if ( a2 > 0x7FFFFFFF )
    return 87;
  if ( a2 < 0x104 )
    return 122;
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, a1, a2);
  v8 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath >= 0 )
    goto LABEL_9;
  if ( (BasicProfileFolderPath & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)BasicProfileFolderPath;
  if ( !v8 )
  {
LABEL_9:
    v9 = L"Profiles";
    if ( a3 )
      v9 = L"DMProfiles";
    v10 = StringCchPrintfW(a1, a2, L"%s\\%s\\%s", a1, L"Microsoft\\WwanSvc", v9);
    v8 = v10;
    if ( v10 < 0 )
    {
      if ( (v10 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v10;
    }
    else
    {
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000e0e0  mov     [rsp+arg_0], rbx
0x18000e0e5  mov     [rsp+arg_8], rsi
0x18000e0ea  push    rdi
0x18000e0eb  sub     rsp, 30h
0x18000e0ef  xor     eax, eax
0x18000e0f1  mov     esi, r8d
0x18000e0f4  mov     [rcx], ax
0x18000e0f7  mov     rbx, rdx
0x18000e0fa  mov     rdi, rcx
0x18000e0fd  cmp     rdx, 7FFFFFFFh
0x18000e104  jbe     short loc_18000E110
0x18000e106  mov     eax, 57h ; 'W'
0x18000e10b  jmp     loc_18000E19F
0x18000e110  cmp     rbx, 104h
0x18000e117  jnb     short loc_18000E120
0x18000e119  mov     eax, 7Ah ; 'z'
0x18000e11e  jmp     short loc_18000E19F
0x18000e120  xor     edx, edx
0x18000e122  mov     r9, rbx
0x18000e125  mov     r8, rdi
0x18000e128  lea     ecx, [rdx+4]
0x18000e12b  call    cs:__imp_GetBasicProfileFolderPath
0x18000e131  mov     ecx, eax
0x18000e133  test    eax, eax
0x18000e135  jns     short loc_18000E14A
0x18000e137  and     eax, 1FFF0000h
0x18000e13c  cmp     eax, 70000h
0x18000e141  jnz     short loc_18000E146
0x18000e143  movzx   ecx, cx
0x18000e146  test    ecx, ecx
0x18000e148  jnz     short loc_18000E19D
0x18000e14a  lea     rcx, aDmprofiles; "DMProfiles"
0x18000e151  test    esi, esi
0x18000e153  lea     rax, aProfiles; "Profiles"
0x18000e15a  mov     r9, rdi
0x18000e15d  cmovnz  rax, rcx
0x18000e161  lea     r8, aSSS; "%s\\%s\\%s"
0x18000e168  mov     [rsp+38h+var_10], rax
0x18000e16d  mov     rdx, rbx; unsigned __int64
0x18000e170  lea     rax, aMicrosoftWwans; "Microsoft\\WwanSvc"
0x18000e177  mov     rcx, rdi; unsigned __int16 *
0x18000e17a  mov     [rsp+38h+var_18], rax
0x18000e17f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e184  mov     ecx, eax
0x18000e186  test    eax, eax
0x18000e188  js      short loc_18000E18E
0x18000e18a  xor     ecx, ecx
0x18000e18c  jmp     short loc_18000E19D
0x18000e18e  and     eax, 1FFF0000h
0x18000e193  cmp     eax, 70000h
0x18000e198  jnz     short loc_18000E19D
0x18000e19a  movzx   ecx, cx
0x18000e19d  mov     eax, ecx
0x18000e19f  mov     rbx, [rsp+38h+arg_0]
0x18000e1a4  mov     rsi, [rsp+38h+arg_8]
0x18000e1a9  add     rsp, 30h
0x18000e1ad  pop     rdi
0x18000e1ae  retn
```
