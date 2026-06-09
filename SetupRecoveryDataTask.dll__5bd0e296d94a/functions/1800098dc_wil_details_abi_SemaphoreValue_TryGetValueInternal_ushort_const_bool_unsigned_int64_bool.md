# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800098dc`
- end: `0x180009b48`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003940`
- `0x180003ce4`

## callees

- `0x180005c34`
- `0x180008a14`
- `0x180008a34`
- `0x1800093d0`
- `0x1800098dc`
- `0x18000ab1c`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009970`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009970`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a8e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x1800098dc  push    rbp
0x1800098de  push    rbx
0x1800098df  push    rsi
0x1800098e0  push    rdi
0x1800098e1  push    r14
0x1800098e3  push    r15
0x1800098e5  lea     rbp, [rsp-158h]
0x1800098ed  sub     rsp, 258h
0x1800098f4  mov     rax, cs:__security_cookie
0x1800098fb  xor     rax, rsp
0x1800098fe  mov     [rbp+180h+var_40], rax
0x180009905  xor     r15d, r15d
0x180009908  lea     rax, [rsp+280h+Name]
0x18000990d  mov     [r8], r15
0x180009910  mov     r14, r8
0x180009913  mov     edx, 104h
0x180009918  mov     r9d, 7FFFFFFEh
0x18000991e  test    r9, r9
0x180009921  jz      short loc_180009942
0x180009923  movzx   r8d, word ptr [rcx]
0x180009927  test    r8w, r8w
0x18000992b  jz      short loc_180009942
0x18000992d  mov     [rax], r8w
0x180009931  add     rcx, 2
0x180009935  add     rax, 2
0x180009939  dec     r9
0x18000993c  sub     rdx, 1; unsigned __int64
0x180009940  jnz     short loc_18000991E
0x180009942  test    rdx, rdx
0x180009945  lea     rcx, [rax-2]
0x180009949  lea     r8, aP0; "_p0"
0x180009950  cmovnz  rcx, rax
0x180009954  mov     [rcx], r15w
0x180009958  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000995d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009962  mov     esi, 1F0003h
0x180009967  lea     r8, [rsp+280h+Name]; lpName
0x18000996c  mov     ecx, esi; dwDesiredAccess
0x18000996e  xor     edx, edx; bInheritHandle
0x180009970  call    cs:__imp_OpenSemaphoreW
0x180009976  mov     rbx, rax
0x180009979  test    rax, rax
0x18000997c  jz      loc_180009A9D
0x180009982  lea     rdx, [rsp+280h+var_25C]; int *
0x180009987  mov     [rsp+280h+var_25C], r15d
0x18000998c  mov     rcx, rax; hHandle
0x18000998f  mov     [rsp+280h+var_260], r15d; int
0x180009994  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009999  mov     edi, eax
0x18000999b  test    eax, eax
0x18000999d  jns     short loc_1800099CB
0x18000999f  mov     rcx, [rbp+188h]; this
0x1800099a6  mov     r9d, eax; char *
0x1800099a9  mov     edx, 0D6h; void *
0x1800099ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099b3  mov     rcx, rbx; hObject
0x1800099b6  call    cs:__imp_CloseHandle
0x1800099bc  test    eax, eax
0x1800099be  jz      loc_180009B12
0x1800099c4  mov     eax, edi
0x1800099c6  jmp     loc_180009ABD
0x1800099cb  lea     r8, asc_180010258; "h"
0x1800099d2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800099d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800099dc  lea     r8, [rsp+280h+Name]; lpName
0x1800099e1  xor     edx, edx; bInheritHandle
0x1800099e3  mov     ecx, esi; dwDesiredAccess
0x1800099e5  call    cs:__imp_OpenSemaphoreW
0x1800099eb  mov     rdi, rax
0x1800099ee  test    rax, rax
0x1800099f1  jz      loc_180009A78
0x1800099f7  lea     rdx, [rsp+280h+var_260]; int *
0x1800099fc  mov     rcx, rax; hHandle
0x1800099ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009a04  mov     esi, eax
0x180009a06  test    eax, eax
0x180009a08  jns     short loc_180009A44
0x180009a0a  mov     rcx, [rbp+188h]; this
0x180009a11  mov     r9d, eax; char *
0x180009a14  mov     edx, 0DEh; void *
0x180009a19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a1e  mov     rcx, rdi; hObject
0x180009a21  call    cs:__imp_CloseHandle
0x180009a27  test    eax, eax
0x180009a29  jz      loc_180009B24
0x180009a2f  mov     rcx, rbx; hObject
0x180009a32  call    cs:__imp_CloseHandle
0x180009a38  test    eax, eax
0x180009a3a  jz      loc_180009B36
0x180009a40  mov     eax, esi
0x180009a42  jmp     short loc_180009ABD
0x180009a44  mov     rcx, rdi; hObject
0x180009a47  call    cs:__imp_CloseHandle
0x180009a4d  test    eax, eax
0x180009a4f  jz      loc_180009ADC
0x180009a55  movsxd  rax, [rsp+280h+var_25C]
0x180009a5a  movsxd  rcx, [rsp+280h+var_260]
0x180009a5f  shl     rcx, 1Fh
0x180009a63  or      rcx, rax
0x180009a66  mov     [r14], rcx
0x180009a69  mov     rcx, rbx; hObject
0x180009a6c  call    cs:__imp_CloseHandle
0x180009a72  test    eax, eax
0x180009a74  jz      short loc_180009AEE
0x180009a76  jmp     short loc_180009AA8
0x180009a78  mov     rcx, [rbp+188h]; this
0x180009a7f  mov     edx, 0DCh; void *
0x180009a84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009a89  mov     rcx, rbx; hObject
0x180009a8c  mov     edi, eax
0x180009a8e  call    cs:__imp_CloseHandle
0x180009a94  test    eax, eax
0x180009a96  jz      short loc_180009B00
0x180009a98  jmp     loc_1800099C4
0x180009a9d  call    cs:__imp_GetLastError
0x180009aa3  cmp     eax, 2
0x180009aa6  jnz     short loc_180009AAC
0x180009aa8  xor     eax, eax
0x180009aaa  jmp     short loc_180009ABD
0x180009aac  mov     rcx, [rbp+188h]; this
0x180009ab3  mov     edx, 0D0h; void *
0x180009ab8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009abd  mov     rcx, [rbp+180h+var_40]
0x180009ac4  xor     rcx, rsp; StackCookie
0x180009ac7  call    __security_check_cookie
0x180009acc  add     rsp, 258h
0x180009ad3  pop     r15
0x180009ad5  pop     r14
0x180009ad7  pop     rdi
0x180009ad8  pop     rsi
0x180009ad9  pop     rbx
0x180009ada  pop     rbp
0x180009adb  retn
0x180009adc  mov     rcx, [rbp+188h]; this
0x180009ae3  mov     edx, 0A0Bh; void *
0x180009ae8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009aee  mov     rcx, [rbp+188h]; this
0x180009af5  mov     edx, 0A0Bh; void *
0x180009afa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b00  mov     rcx, [rbp+188h]; this
0x180009b07  mov     edx, 0A0Bh; void *
0x180009b0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b12  mov     rcx, [rbp+188h]; this
0x180009b19  mov     edx, 0A0Bh; void *
0x180009b1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b24  mov     rcx, [rbp+188h]; this
0x180009b2b  mov     edx, 0A0Bh; void *
0x180009b30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b36  mov     rcx, [rbp+188h]; this
0x180009b3d  mov     edx, 0A0Bh; void *
0x180009b42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
