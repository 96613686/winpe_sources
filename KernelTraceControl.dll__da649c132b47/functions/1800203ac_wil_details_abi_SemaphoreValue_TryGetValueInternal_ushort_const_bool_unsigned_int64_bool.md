# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800203ac`
- end: `0x1800205f6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `586`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180023288`

## callees

- `0x18001dd1c`
- `0x18002018c`
- `0x1800201c4`
- `0x1800201dc`
- `0x180020268`
- `0x1800203ac`
- `0x180026e30`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180020457`
- `KERNEL32!OpenSemaphoreW` at `0x1800204f3`
- `KERNEL32!OpenSemaphoreW` at `0x180020457`
- `KERNEL32!OpenSemaphoreW` at `0x1800204f3`
- `KERNEL32!GetLastError` at `0x18002046a`
- `KERNEL32!GetLastError` at `0x18002046a`
- `KERNEL32!CloseHandle` at `0x180020552`
- `KERNEL32!CloseHandle` at `0x180020571`
- `KERNEL32!CloseHandle` at `0x1800205ac`
- `KERNEL32!CloseHandle` at `0x180020552`
- `KERNEL32!CloseHandle` at `0x180020571`
- `KERNEL32!CloseHandle` at `0x1800205ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r9
  WCHAR *v6; // rdx
  signed __int64 v7; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rdi
  const char *v12; // r9
  unsigned int LastError; // esi
  int ValueFromSemaphore; // eax
  unsigned int v15; // r8d
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rbx
  int v19; // eax
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  int v28[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+30h] [rbp-D8h]
  HANDLE v30; // [rsp+38h] [rbp-D0h]
  HANDLE v31; // [rsp+40h] [rbp-C8h]
  WCHAR Name[264]; // [rsp+48h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v29 = -2;
  *a3 = 0;
  v5 = 260;
  v6 = Name;
  v7 = a1 - (char *)Name;
  do
  {
    if ( v5 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v6 + v7);
    if ( !v8 )
      break;
    *v6++ = v8;
    --v5;
  }
  while ( v5 );
  v9 = v6 - 1;
  if ( v5 )
    v9 = v6;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  v30 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xC8, (unsigned int)"wil", v12);
      goto LABEL_23;
    }
LABEL_22:
    LastError = 0;
    goto LABEL_23;
  }
  v28[1] = 0;
  v28[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v28[1]);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr_NoOriginate(
      retaddr,
      (void *)0xCE,
      v15,
      (const char *)(unsigned int)ValueFromSemaphore,
      v28[0]);
    goto LABEL_23;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  v31 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v28);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
      {
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x875, v23, v24);
        __debugbreak();
      }
      *a3 = ((__int64)v28[0] << 31) | v28[1];
      goto LABEL_22;
    }
    wil::details::in1diag3::Return_Hr_NoOriginate(retaddr, (void *)0xD6, v20, (const char *)(unsigned int)v19, v28[0]);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD4, (unsigned int)"wil", v17);
  }
  if ( v18 && !CloseHandle(v18) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x875, v21, v22);
    __debugbreak();
  }
LABEL_23:
  if ( v11 && !CloseHandle(v11) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x875, v25, v26);
    __debugbreak();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800203ac  mov     rax, rsp
0x1800203af  push    rbp
0x1800203b0  push    r14
0x1800203b2  push    r15
0x1800203b4  lea     rbp, [rax-178h]
0x1800203bb  sub     rsp, 260h
0x1800203c2  mov     [rsp+270h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800203cb  mov     [rax+8], rbx
0x1800203cf  mov     [rax+10h], rsi
0x1800203d3  mov     [rax+20h], rdi
0x1800203d7  mov     rax, cs:__security_cookie
0x1800203de  xor     rax, rsp
0x1800203e1  mov     [rbp+170h+var_20], rax
0x1800203e8  mov     r14, r8
0x1800203eb  xor     r15d, r15d
0x1800203ee  mov     [r8], r15
0x1800203f1  mov     ebx, 104h
0x1800203f6  mov     r9d, ebx
0x1800203f9  lea     rdx, [rsp+270h+Name]
0x1800203fe  lea     rax, [rsp+270h+Name]
0x180020403  sub     rcx, rax
0x180020406  lea     rax, [r9+7FFFFEFAh]
0x18002040d  test    rax, rax
0x180020410  jz      short loc_180020428
0x180020412  movzx   eax, word ptr [rcx+rdx]
0x180020416  test    ax, ax
0x180020419  jz      short loc_180020428
0x18002041b  mov     [rdx], ax
0x18002041e  add     rdx, 2
0x180020422  sub     r9, 1
0x180020426  jnz     short loc_180020406
0x180020428  lea     rax, [rdx-2]
0x18002042c  test    r9, r9
0x18002042f  cmovnz  rax, rdx
0x180020433  mov     [rax], r15w
0x180020437  lea     r8, aP0; "_p0"
0x18002043e  mov     rdx, rbx; unsigned __int64
0x180020441  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180020446  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002044b  lea     r8, [rsp+270h+Name]; lpName
0x180020450  xor     edx, edx; bInheritHandle
0x180020452  mov     ecx, 1F0003h; dwDesiredAccess
0x180020457  call    cs:__imp_OpenSemaphoreW
0x18002045d  mov     rdi, rax
0x180020460  mov     [rsp+270h+var_240], rax
0x180020465  test    rax, rax
0x180020468  jnz     short loc_18002049D
0x18002046a  call    cs:__imp_GetLastError
0x180020470  cmp     eax, 2
0x180020473  setz    al
0x180020476  test    al, al
0x180020478  jnz     loc_1800205A1
0x18002047e  mov     rcx, [rbp+178h]; this
0x180020485  lea     r8, aWil; "wil"
0x18002048c  mov     edx, 0C8h; void *
0x180020491  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020496  mov     esi, eax
0x180020498  jmp     loc_1800205A4
0x18002049d  mov     [rsp+270h+var_250+4], r15d
0x1800204a2  mov     [rsp+270h+var_250], r15d; int
0x1800204a7  lea     rdx, [rsp+270h+var_250+4]; int *
0x1800204ac  mov     rcx, rdi; hHandle
0x1800204af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800204b4  mov     esi, eax
0x1800204b6  test    eax, eax
0x1800204b8  jns     short loc_1800204D3
0x1800204ba  mov     rcx, [rbp+178h]; this
0x1800204c1  mov     r9d, eax; char *
0x1800204c4  mov     edx, 0CEh; void *
0x1800204c9  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x1800204ce  jmp     loc_1800205A4
0x1800204d3  lea     r8, asc_18002D628; "h"
0x1800204da  mov     rdx, rbx; unsigned __int64
0x1800204dd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800204e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800204e7  lea     r8, [rsp+270h+Name]; lpName
0x1800204ec  xor     edx, edx; bInheritHandle
0x1800204ee  mov     ecx, 1F0003h; dwDesiredAccess
0x1800204f3  call    cs:__imp_OpenSemaphoreW
0x1800204f9  mov     rbx, rax
0x1800204fc  mov     [rsp+270h+var_238], rax
0x180020501  test    rax, rax
0x180020504  jnz     short loc_180020522
0x180020506  mov     rcx, [rbp+178h]; this
0x18002050d  lea     r8, aWil; "wil"
0x180020514  mov     edx, 0D4h; void *
0x180020519  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002051e  mov     esi, eax
0x180020520  jmp     short loc_18002054A
0x180020522  lea     rdx, [rsp+270h+var_250]; int *
0x180020527  mov     rcx, rbx; hHandle
0x18002052a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002052f  mov     esi, eax
0x180020531  test    eax, eax
0x180020533  jns     short loc_18002056E
0x180020535  mov     rcx, [rbp+178h]; this
0x18002053c  mov     r9d, eax; char *
0x18002053f  mov     edx, 0D6h; void *
0x180020544  call    ?Return_Hr_NoOriginate@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr_NoOriginate(void *,uint,char const *,long)
0x180020549  nop
0x18002054a  test    rbx, rbx
0x18002054d  jz      short loc_1800205A4
0x18002054f  mov     rcx, rbx; hObject
0x180020552  call    cs:__imp_CloseHandle
0x180020558  mov     rcx, [rbp+178h]; this
0x18002055f  test    eax, eax
0x180020561  jnz     short loc_1800205A4
0x180020563  mov     edx, 875h; void *
0x180020568  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002056d  int     3; Trap to Debugger
0x18002056e  mov     rcx, rbx; hObject
0x180020571  call    cs:__imp_CloseHandle
0x180020577  mov     rcx, [rbp+178h]; this
0x18002057e  test    eax, eax
0x180020580  jnz     short loc_18002058D
0x180020582  mov     edx, 875h; void *
0x180020587  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002058c  int     3; Trap to Debugger
0x18002058d  movsxd  rcx, [rsp+270h+var_250]
0x180020592  shl     rcx, 1Fh
0x180020596  movsxd  rax, [rsp+270h+var_250+4]
0x18002059b  or      rax, rcx
0x18002059e  mov     [r14], rax
0x1800205a1  mov     esi, r15d
0x1800205a4  test    rdi, rdi
0x1800205a7  jz      short loc_1800205C8
0x1800205a9  mov     rcx, rdi; hObject
0x1800205ac  call    cs:__imp_CloseHandle
0x1800205b2  test    eax, eax
0x1800205b4  jnz     short loc_1800205C8
0x1800205b6  mov     rcx, [rbp+178h]; this
0x1800205bd  mov     edx, 875h; void *
0x1800205c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800205c7  int     3; Trap to Debugger
0x1800205c8  mov     eax, esi
0x1800205ca  mov     rcx, [rbp+170h+var_20]
0x1800205d1  xor     rcx, rsp; StackCookie
0x1800205d4  call    __security_check_cookie
0x1800205d9  lea     r11, [rsp+270h+var_10]
0x1800205e1  mov     rbx, [r11+20h]
0x1800205e5  mov     rsi, [r11+28h]
0x1800205e9  mov     rdi, [r11+38h]
0x1800205ed  mov     rsp, r11
0x1800205f0  pop     r15
0x1800205f2  pop     r14
0x1800205f4  pop     rbp
0x1800205f5  retn
```
