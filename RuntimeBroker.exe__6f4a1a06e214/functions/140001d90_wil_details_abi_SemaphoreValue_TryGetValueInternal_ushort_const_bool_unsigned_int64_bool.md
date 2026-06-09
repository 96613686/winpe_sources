# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140001d90`
- end: `0x140002071`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `737`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140001a4c`
- `0x140001ad0`

## callees

- `0x140001d90`
- `0x140002080`
- `0x14000222c`
- `0x1400027ac`
- `0x140007f38`
- `0x140008c80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140001e30`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140001ee0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140001e30`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140001ee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001e3e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // r9
  __int64 v5; // rbp
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r10
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  wil::details *v13; // rax
  wil::details *v14; // rdi
  const char *v15; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  WCHAR *v19; // rax
  wil::details *v20; // rax
  const char *v21; // r9
  wil::details *v22; // rbx
  void *v23; // rdx
  __int64 v24; // rcx
  _WORD *v25; // r8
  const unsigned __int16 *v26; // r9
  _WORD *v27; // rcx
  int v28; // eax
  void *v29; // rdx
  unsigned int v30; // esi
  void *v31; // rdx
  _WORD *v32; // r8
  const unsigned __int16 *v33; // rcx
  _WORD *v34; // rdx
  void *v35; // rdx
  void *v36; // rdx
  int v37; // [rsp+20h] [rbp-248h] BYREF
  int v38[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[260]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v40[8]; // [rsp+238h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  v8 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v10 = v4 - 1;
  v11 = 260;
  v12 = Name;
  if ( v8 )
    v10 = v4;
  *v10 = 0;
  while ( *v12 )
  {
    ++v12;
    if ( !--v11 )
      goto LABEL_10;
  }
  v24 = 2147483646;
  v25 = &v40[-2 * v11];
  v26 = L"_p0";
  do
  {
    if ( !v24 )
      break;
    if ( !*v26 )
      break;
    *v25++ = *v26++;
    --v24;
    --v11;
  }
  while ( v11 );
  v27 = v25 - 1;
  if ( v11 )
    v27 = v25;
  *v27 = 0;
LABEL_10:
  v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v14 = v13;
  if ( !v13 )
  {
    if ( GetLastError() == 2 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v15);
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v37);
    goto LABEL_20;
  }
  v19 = Name;
  while ( *v19 )
  {
    ++v19;
    if ( !--v6 )
      goto LABEL_18;
  }
  v32 = &v40[-2 * v6];
  v33 = L"h";
  do
  {
    if ( !v5 )
      break;
    if ( !*v33 )
      break;
    *v32++ = *v33++;
    --v5;
    --v6;
  }
  while ( v6 );
  v34 = v32 - 1;
  if ( v6 )
    v34 = v32;
  *v34 = 0;
LABEL_18:
  v20 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v20;
  if ( !v20 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v21);
LABEL_20:
    wil::details::CloseHandle(v14, v23);
    return LastError;
  }
  v28 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v37);
  v30 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v28, v37);
    wil::details::CloseHandle(v22, v35);
    wil::details::CloseHandle(v14, v36);
    return v30;
  }
  else
  {
    wil::details::CloseHandle(v22, v29);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    wil::details::CloseHandle(v14, v31);
    return 0;
  }
}

```

## disassembly

```asm
0x140001d90  mov     [rsp+arg_8], rbp
0x140001d95  mov     [rsp+arg_18], rsi
0x140001d9a  push    rdi
0x140001d9b  push    r14
0x140001d9d  push    r15
0x140001d9f  sub     rsp, 250h
0x140001da6  mov     rax, cs:__security_cookie
0x140001dad  xor     rax, rsp
0x140001db0  mov     [rsp+268h+var_28], rax
0x140001db8  xor     r15d, r15d
0x140001dbb  lea     r9, [rsp+268h+Name]
0x140001dc0  mov     ebp, 7FFFFFFEh
0x140001dc5  mov     [r8], r15
0x140001dc8  mov     esi, 104h
0x140001dcd  mov     edx, ebp
0x140001dcf  mov     r10d, esi
0x140001dd2  mov     r14, r8
0x140001dd5  test    rdx, rdx
0x140001dd8  jz      short loc_140001DF7
0x140001dda  movzx   eax, word ptr [rcx]
0x140001ddd  test    ax, ax
0x140001de0  jz      short loc_140001DF7
0x140001de2  mov     [r9], ax
0x140001de6  add     rcx, 2
0x140001dea  add     r9, 2
0x140001dee  dec     rdx
0x140001df1  sub     r10, 1
0x140001df5  jnz     short loc_140001DD5
0x140001df7  test    r10, r10
0x140001dfa  lea     rcx, [r9-2]
0x140001dfe  mov     rdx, rsi
0x140001e01  lea     rax, [rsp+268h+Name]
0x140001e06  cmovnz  rcx, r9
0x140001e0a  mov     [rcx], r15w
0x140001e0e  xchg    ax, ax
0x140001e10  cmp     [rax], r15w
0x140001e14  jz      loc_140001F24
0x140001e1a  add     rax, 2
0x140001e1e  sub     rdx, 1
0x140001e22  jnz     short loc_140001E10
0x140001e24  lea     r8, [rsp+268h+Name]; lpName
0x140001e29  xor     edx, edx; bInheritHandle
0x140001e2b  mov     ecx, 1F0003h; dwDesiredAccess
0x140001e30  call    cs:__imp_OpenSemaphoreW
0x140001e36  mov     rdi, rax
0x140001e39  test    rax, rax
0x140001e3c  jnz     short loc_140001E8F
0x140001e3e  call    cs:__imp_GetLastError
0x140001e44  cmp     eax, 2
0x140001e47  jz      short loc_140001E8B
0x140001e49  mov     rcx, [rsp+268h]; this
0x140001e51  lea     r8, aWil; "wil"
0x140001e58  mov     edx, 0D0h; void *
0x140001e5d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140001e62  mov     rcx, [rsp+268h+var_28]
0x140001e6a  xor     rcx, rsp; StackCookie
0x140001e6d  call    __security_check_cookie
0x140001e72  lea     r11, [rsp+268h+var_18]
0x140001e7a  mov     rbp, [r11+28h]
0x140001e7e  mov     rsi, [r11+38h]
0x140001e82  mov     rsp, r11
0x140001e85  pop     r15
0x140001e87  pop     r14
0x140001e89  pop     rdi
0x140001e8a  retn
0x140001e8b  xor     eax, eax
0x140001e8d  jmp     short loc_140001E62
0x140001e8f  lea     rdx, [rsp+268h+var_244]; int *
0x140001e94  mov     [rsp+268h+arg_0], rbx
0x140001e9c  mov     rcx, rdi; hHandle
0x140001e9f  mov     [rsp+268h+var_244], r15d
0x140001ea4  mov     [rsp+268h+var_248], r15d; int
0x140001ea9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140001eae  mov     ebx, eax
0x140001eb0  test    eax, eax
0x140001eb2  js      loc_140001FC3
0x140001eb8  lea     rax, [rsp+268h+Name]
0x140001ebd  nop     dword ptr [rax]
0x140001ec0  cmp     [rax], r15w
0x140001ec4  jz      loc_140001FE4
0x140001eca  add     rax, 2
0x140001ece  sub     rsi, 1
0x140001ed2  jnz     short loc_140001EC0
0x140001ed4  lea     r8, [rsp+268h+Name]; lpName
0x140001ed9  xor     edx, edx; bInheritHandle
0x140001edb  mov     ecx, 1F0003h; dwDesiredAccess
0x140001ee0  call    cs:__imp_OpenSemaphoreW
0x140001ee6  mov     rbx, rax
0x140001ee9  test    rax, rax
0x140001eec  jnz     loc_140001F79
0x140001ef2  mov     rcx, [rsp+268h]; this
0x140001efa  lea     r8, aWil; "wil"
0x140001f01  mov     edx, 0DCh; void *
0x140001f06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140001f0b  mov     ebx, eax
0x140001f0d  mov     rcx, rdi; this
0x140001f10  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140001f15  mov     eax, ebx
0x140001f17  mov     rbx, [rsp+268h+arg_0]
0x140001f1f  jmp     loc_140001E62
0x140001f24  lea     rax, [rdx+rdx]
0x140001f28  mov     rcx, rbp
0x140001f2b  lea     r8, [rsp+268h+var_30]
0x140001f33  sub     r8, rax
0x140001f36  lea     r9, aP0; "_p0"
0x140001f3d  test    rdx, rdx
0x140001f40  jz      short loc_140001F65
0x140001f42  test    rcx, rcx
0x140001f45  jz      short loc_140001F65
0x140001f47  movzx   eax, word ptr [r9]
0x140001f4b  test    ax, ax
0x140001f4e  jz      short loc_140001F65
0x140001f50  mov     [r8], ax
0x140001f54  add     r9, 2
0x140001f58  add     r8, 2
0x140001f5c  dec     rcx
0x140001f5f  sub     rdx, 1
0x140001f63  jnz     short loc_140001F42
0x140001f65  test    rdx, rdx
0x140001f68  lea     rcx, [r8-2]
0x140001f6c  cmovnz  rcx, r8
0x140001f70  mov     [rcx], r15w
0x140001f74  jmp     loc_140001E24
0x140001f79  lea     rdx, [rsp+268h+var_248]; int *
0x140001f7e  mov     rcx, rbx; hHandle
0x140001f81  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140001f86  mov     esi, eax
0x140001f88  test    eax, eax
0x140001f8a  js      loc_140002036
0x140001f90  mov     rcx, rbx; this
0x140001f93  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140001f98  movsxd  rax, [rsp+268h+var_244]
0x140001f9d  movsxd  rcx, [rsp+268h+var_248]
0x140001fa2  shl     rcx, 1Fh
0x140001fa6  or      rcx, rax
0x140001fa9  mov     [r14], rcx
0x140001fac  mov     rcx, rdi; this
0x140001faf  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140001fb4  mov     rbx, [rsp+268h+arg_0]
0x140001fbc  xor     eax, eax
0x140001fbe  jmp     loc_140001E62
0x140001fc3  mov     rcx, [rsp+268h]; this
0x140001fcb  lea     r8, aWil; "wil"
0x140001fd2  mov     r9d, ebx; char *
0x140001fd5  mov     edx, 0D6h; void *
0x140001fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001fdf  jmp     loc_140001F0D
0x140001fe4  lea     rax, [rsi+rsi]
0x140001fe8  lea     r8, [rsp+268h+var_30]
0x140001ff0  sub     r8, rax
0x140001ff3  lea     rcx, asc_140012E3C; "h"
0x140001ffa  test    rsi, rsi
0x140001ffd  jz      short loc_140002022
0x140001fff  nop
0x140002000  test    rbp, rbp
0x140002003  jz      short loc_140002022
0x140002005  movzx   eax, word ptr [rcx]
0x140002008  test    ax, ax
0x14000200b  jz      short loc_140002022
0x14000200d  mov     [r8], ax
0x140002011  add     rcx, 2
0x140002015  add     r8, 2
0x140002019  dec     rbp
0x14000201c  sub     rsi, 1
0x140002020  jnz     short loc_140002000
0x140002022  test    rsi, rsi
0x140002025  lea     rdx, [r8-2]
0x140002029  cmovnz  rdx, r8
0x14000202d  mov     [rdx], r15w
0x140002031  jmp     loc_140001ED4
0x140002036  mov     rcx, [rsp+268h]; this
0x14000203e  lea     r8, aWil; "wil"
0x140002045  mov     r9d, esi; char *
0x140002048  mov     edx, 0DEh; void *
0x14000204d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002052  mov     rcx, rbx; this
0x140002055  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000205a  mov     rcx, rdi; this
0x14000205d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002062  mov     rbx, [rsp+268h+arg_0]
0x14000206a  mov     eax, esi
0x14000206c  jmp     loc_140001E62
```
