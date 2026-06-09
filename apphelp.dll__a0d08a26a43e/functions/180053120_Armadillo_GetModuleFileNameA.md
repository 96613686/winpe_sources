# Armadillo_GetModuleFileNameA

- ea: `0x180053120`
- end: `0x18005323a`
- name: `Armadillo_GetModuleFileNameA`
- size: `282`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000f114`
- `0x180053120`
- `0x180053f54`
- `0x180054034`
- `0x18005a010`

## import_xrefs

- `ntdll!strrchr` at `0x180053172`
- `ntdll!strrchr` at `0x180053172`
- `ntdll!_stricmp` at `0x18005319c`
- `ntdll!_stricmp` at `0x18005319c`

## string_xrefs

- `0x180053192`: `\apphelp.dll`
- `0x1800531da`: `\shimeng.dll`
- `0x180053211`: `Failed to StringCchCopyNA`

## pseudocode

```c
__int64 __fastcall Armadillo_GetModuleFileNameA(__int64 a1, char *a2, unsigned int a3)
{
  size_t v4; // rbp
  __int64 v5; // rdi
  int v6; // eax
  char *v7; // rax
  char *v8; // rsi
  size_t *v9; // r8
  size_t cchToCopy; // rsi

  v4 = a3;
  if ( !qword_180080198 )
  {
    LODWORD(v5) = 0;
    AslLogCallPrintf(1, "Armadillo_GetModuleFileNameA", 477, "Failed to get hook to the original API");
    return (unsigned int)v5;
  }
  v6 = qword_180080198(a1, a2, a3);
  LODWORD(v5) = v6;
  if ( a2 && v6 )
  {
    v7 = strrchr(a2, 92);
    v8 = v7;
    if ( !v7 )
    {
      AslLogCallPrintf(1, "Armadillo_GetModuleFileNameA", 490, "Failed to find a slash in lpFileName");
      return (unsigned int)v5;
    }
    if ( _stricmp(v7, "\\apphelp.dll") )
      return (unsigned int)v5;
    if ( (_DWORD)v4 )
    {
      if ( v4 > 0x7FFFFFFF || (cchToCopy = v8 - a2, cchToCopy > 0x7FFFFFFE) )
      {
        *a2 = 0;
      }
      else if ( StringCopyWorkerA(a2, v4, v9, a2, cchToCopy) >= 0 )
      {
        if ( StringCchCatA(a2, v4, "\\shimeng.dll") >= 0 )
        {
          v5 = -1;
          do
            ++v5;
          while ( a2[v5] );
        }
        else
        {
          AslLogCallPrintf(1, "Armadillo_GetModuleFileNameA", 504, "Failed to StringCchCatA");
        }
        return (unsigned int)v5;
      }
    }
    AslLogCallPrintf(1, "Armadillo_GetModuleFileNameA", 499, "Failed to StringCchCopyNA");
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180053120  push    rbx
0x180053122  push    rbp
0x180053123  push    rsi
0x180053124  push    rdi
0x180053125  sub     rsp, 38h
0x180053129  mov     rax, cs:qword_180080198
0x180053130  mov     rbx, rdx
0x180053133  mov     ebp, r8d
0x180053136  test    rax, rax
0x180053139  jnz     short loc_18005314F
0x18005313b  xor     edi, edi
0x18005313d  lea     r9, aFailedToGetHoo; "Failed to get hook to the original API"
0x180053144  mov     r8d, 1DDh
0x18005314a  jmp     loc_18005321E
0x18005314f  mov     r8d, ebp
0x180053152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053157  mov     edi, eax
0x180053159  test    rbx, rbx
0x18005315c  jz      loc_18005322F
0x180053162  test    eax, eax
0x180053164  jz      loc_18005322F
0x18005316a  mov     edx, 5Ch ; '\'; Ch
0x18005316f  mov     rcx, rbx; Str
0x180053172  call    cs:__imp_strrchr
0x180053178  mov     rsi, rax
0x18005317b  test    rax, rax
0x18005317e  jnz     short loc_180053192
0x180053180  lea     r9, aFailedToFindAS; "Failed to find a slash in lpFileName"
0x180053187  mov     r8d, 1EAh
0x18005318d  jmp     loc_18005321E
0x180053192  lea     rdx, aApphelpDll_0; "\\apphelp.dll"
0x180053199  mov     rcx, rsi; String1
0x18005319c  call    cs:__imp__stricmp
0x1800531a2  test    eax, eax
0x1800531a4  jnz     loc_18005322F
0x1800531aa  test    ebp, ebp
0x1800531ac  jz      short loc_180053211
0x1800531ae  cmp     rbp, 7FFFFFFFh
0x1800531b5  ja      short loc_18005320E
0x1800531b7  sub     rsi, rbx
0x1800531ba  cmp     rsi, 7FFFFFFEh
0x1800531c1  ja      short loc_18005320E
0x1800531c3  mov     r9, rbx; pszSrc
0x1800531c6  mov     [rsp+58h+cchToCopy], rsi; cchToCopy
0x1800531cb  mov     rdx, rbp; cchDest
0x1800531ce  mov     rcx, rbx; pszDest
0x1800531d1  call    StringCopyWorkerA
0x1800531d6  test    eax, eax
0x1800531d8  js      short loc_180053211
0x1800531da  lea     r8, aShimengDll; "\\shimeng.dll"
0x1800531e1  mov     rdx, rbp; cchDest
0x1800531e4  mov     rcx, rbx; pszDest
0x1800531e7  call    StringCchCatA
0x1800531ec  test    eax, eax
0x1800531ee  jns     short loc_1800531FF
0x1800531f0  lea     r9, aFailedToString_3; "Failed to StringCchCatA"
0x1800531f7  mov     r8d, 1F8h
0x1800531fd  jmp     short loc_18005321E
0x1800531ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053203  inc     rdi
0x180053206  cmp     byte ptr [rbx+rdi], 0
0x18005320a  jnz     short loc_180053203
0x18005320c  jmp     short loc_18005322F
0x18005320e  mov     byte ptr [rbx], 0
0x180053211  lea     r9, aFailedToString; "Failed to StringCchCopyNA"
0x180053218  mov     r8d, 1F3h
0x18005321e  lea     rdx, aArmadilloGetmo; "Armadillo_GetModuleFileNameA"
0x180053225  mov     ecx, 1
0x18005322a  call    AslLogCallPrintf
0x18005322f  mov     eax, edi
0x180053231  add     rsp, 38h
0x180053235  pop     rdi
0x180053236  pop     rsi
0x180053237  pop     rbp
0x180053238  pop     rbx
0x180053239  retn
```
