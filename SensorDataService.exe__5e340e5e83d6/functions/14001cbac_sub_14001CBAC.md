# sub_14001CBAC

- ea: `0x14001cbac`
- end: `0x14001d13b`
- name: `sub_14001CBAC`
- size: `1423`
- prototype: `__int64 __fastcall(__int64, int *, HSTRING)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x14004ad20`

## callees

- `0x140006f60`
- `0x14000795c`
- `0x140015640`
- `0x140015864`
- `0x140017854`
- `0x14001790c`
- `0x140017f80`
- `0x140018e8c`
- `0x140018f44`
- `0x140019aa0`
- `0x14001b090`
- `0x14001b698`
- `0x14001cbac`
- `0x14001d480`
- `0x14001fab4`
- `0x1400533ec`
- `0x1400ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cc0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cc7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d0c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cc0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cc7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d0c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d103`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001cbed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001cbed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001cd4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001cdc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001cfc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001d027`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001cd4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001cdc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001cfc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001d027`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall sub_14001CBAC(__int64 a1, int *a2, HSTRING a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-908h] BYREF
  __int64 v14; // [rsp+28h] [rbp-900h]
  HSTRING string; // [rsp+30h] [rbp-8F8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-8F0h]
  unsigned int v17; // [rsp+40h] [rbp-8E8h]
  __int128 v18; // [rsp+48h] [rbp-8E0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-8D0h]
  int *v20; // [rsp+60h] [rbp-8C8h] BYREF
  char v21; // [rsp+68h] [rbp-8C0h]
  __int128 *v22; // [rsp+70h] [rbp-8B8h]
  __int64 v23; // [rsp+78h] [rbp-8B0h]
  char v24; // [rsp+80h] [rbp-8A8h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+88h] [rbp-8A0h]
  __int64 v26; // [rsp+90h] [rbp-898h]
  __int64 v27; // [rsp+98h] [rbp-890h]
  int *v28; // [rsp+A0h] [rbp-888h]
  __int64 v29; // [rsp+A8h] [rbp-880h]
  _QWORD v30[7]; // [rsp+B0h] [rbp-878h] BYREF
  _QWORD *v31; // [rsp+E8h] [rbp-840h]

  v20 = a2;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 80);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 80));
  v25 = v6;
  if ( !a2 || !a3 )
  {
    if ( v6 )
      LeaveCriticalSection(v6);
    return 2147942487LL;
  }
  v14 = 0;
  v13 = sub_1400CA010(a3);
  if ( v13 < 0 )
  {
    string = (HSTRING)&v13;
    sub_140018F44(&string);
    v8 = v13;
    v9 = v14;
    if ( v14 )
    {
      v14 = 0;
      sub_1400CA010(v9);
    }
LABEL_9:
    if ( v6 )
      LeaveCriticalSection(v6);
    return v8;
  }
  lpCriticalSection = v6;
  v17 = 0;
  v13 = sub_1400CA010(v14);
  if ( v13 < 0 )
  {
    string = (HSTRING)&v13;
    sub_140017854(&string);
    v8 = v13;
    v10 = v14;
    if ( v14 )
    {
      v14 = 0;
      sub_1400CA010(v10);
    }
    goto LABEL_9;
  }
  v18 = 0;
  v19 = 0;
  string = (HSTRING)v17;
  v22 = &v18;
  v23 = a1;
  v24 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)a1;
  if ( a1 )
    sub_1400CA010(a1);
  string = a3;
  sub_1400CA010(a3);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 196));
  v20 = (int *)a1;
  v21 = 1;
  if ( a1 )
    sub_1400CA010(a1);
  v27 = a1;
  v28 = a2;
  sub_1400CA010(a3);
  v30[0] = &std::_Func_impl_no_alloc<_lambda_dcde832d9f7d587edd7fd97a859e7fc3_,void,>::`vftable';
  v30[1] = a1;
  v26 = 0;
  v30[2] = a1;
  v30[3] = a2;
  v30[4] = a3;
  v29 = 0;
  v31 = v30;
  v11 = sub_14001D480(v30);
  v13 = v11;
  if ( v31 )
  {
    sub_1400CA010(v31);
    v11 = v13;
  }
  if ( v11 < 0 )
  {
    v20 = &v13;
    sub_140017F80(&v20);
    v8 = v13;
    sub_14001FAB4(a1);
    sub_1400CA010(a3);
    if ( a1 )
      sub_1400CA010(a1);
    sub_140019AA0(&v18);
    v12 = v14;
    if ( v14 )
    {
      v14 = 0;
      sub_1400CA010(v12);
    }
    goto LABEL_9;
  }
  sub_1400CA010(a3);
  if ( a1 )
    sub_1400CA010(a1);
  sub_140019AA0(&v18);
  if ( v6 )
    LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x14001cbac  mov     [rsp+arg_8], rbx
0x14001cbb1  mov     [rsp+arg_18], rsi
0x14001cbb6  push    rdi
0x14001cbb7  push    r12
0x14001cbb9  push    r13
0x14001cbbb  push    r14
0x14001cbbd  push    r15
0x14001cbbf  sub     rsp, 900h
0x14001cbc6  mov     rax, cs:__security_cookie
0x14001cbcd  xor     rax, rsp
0x14001cbd0  mov     [rsp+928h+var_38], rax
0x14001cbd8  mov     r12, r8
0x14001cbdb  mov     rbx, rdx
0x14001cbde  mov     [rsp+928h+var_8C8], rdx
0x14001cbe3  mov     r15, rcx
0x14001cbe6  lea     r14, [rcx+50h]
0x14001cbea  mov     rcx, r14; lpCriticalSection
0x14001cbed  call    cs:EnterCriticalSection
0x14001cbf3  mov     [rsp+928h+var_8A0], r14
0x14001cbfb  xor     esi, esi
0x14001cbfd  test    rbx, rbx
0x14001cc00  jz      short loc_14001CC07
0x14001cc02  test    r12, r12
0x14001cc05  jnz     short loc_14001CC1F
0x14001cc07  test    r14, r14
0x14001cc0a  jz      short loc_14001CC15
0x14001cc0c  mov     rcx, r14; lpCriticalSection
0x14001cc0f  call    cs:LeaveCriticalSection
0x14001cc15  mov     eax, 80070057h
0x14001cc1a  jmp     loc_14001D10E
0x14001cc1f  mov     [rsp+928h+var_900], rsi
0x14001cc24  mov     rax, [r12]
0x14001cc28  lea     rdx, [rsp+928h+var_900]
0x14001cc2d  mov     rcx, r12
0x14001cc30  mov     rax, [rax+30h]
0x14001cc34  call    sub_1400CA010
0x14001cc39  mov     [rsp+928h+var_908], eax
0x14001cc3d  test    eax, eax
0x14001cc3f  jns     short loc_14001CC8A
0x14001cc41  lea     rax, [rsp+928h+var_908]
0x14001cc46  mov     [rsp+928h+string], rax
0x14001cc4b  lea     rcx, [rsp+928h+string]
0x14001cc50  call    sub_140018F44
0x14001cc55  mov     ebx, [rsp+928h+var_908]
0x14001cc59  mov     rcx, [rsp+928h+var_900]
0x14001cc5e  test    rcx, rcx
0x14001cc61  jz      short loc_14001CC75
0x14001cc63  mov     [rsp+928h+var_900], rsi
0x14001cc68  mov     rax, [rcx]
0x14001cc6b  mov     rax, [rax+10h]
0x14001cc6f  call    sub_1400CA010
0x14001cc74  nop
0x14001cc75  test    r14, r14
0x14001cc78  jz      short loc_14001CC83
0x14001cc7a  mov     rcx, r14; lpCriticalSection
0x14001cc7d  call    cs:LeaveCriticalSection
0x14001cc83  mov     eax, ebx
0x14001cc85  jmp     loc_14001D10E
0x14001cc8a  mov     [rsp+928h+lpCriticalSection], r14
0x14001cc8f  mov     [rsp+928h+var_8E8], esi
0x14001cc93  mov     rcx, [rsp+928h+var_900]
0x14001cc98  mov     rax, [rcx]
0x14001cc9b  lea     rdx, [rsp+928h+var_8E8]
0x14001cca0  mov     rax, [rax+38h]
0x14001cca4  call    sub_1400CA010
0x14001cca9  mov     [rsp+928h+var_908], eax
0x14001ccad  test    eax, eax
0x14001ccaf  jns     short loc_14001CCE7
0x14001ccb1  lea     rax, [rsp+928h+var_908]
0x14001ccb6  mov     [rsp+928h+string], rax
0x14001ccbb  lea     rcx, [rsp+928h+string]
0x14001ccc0  call    sub_140017854
0x14001ccc5  mov     ebx, [rsp+928h+var_908]
0x14001ccc9  mov     rcx, [rsp+928h+var_900]
0x14001ccce  test    rcx, rcx
0x14001ccd1  jz      short loc_14001CCE5
0x14001ccd3  mov     [rsp+928h+var_900], rsi
0x14001ccd8  mov     rax, [rcx]
0x14001ccdb  mov     rax, [rax+10h]
0x14001ccdf  call    sub_1400CA010
0x14001cce4  nop
0x14001cce5  jmp     short loc_14001CC75
0x14001cce7  xorps   xmm0, xmm0
0x14001ccea  movdqu  [rsp+928h+var_8E0], xmm0
0x14001ccf0  mov     [rsp+928h+var_8D0], rsi
0x14001ccf5  mov     ecx, [rsp+928h+var_8E8]
0x14001ccf9  mov     [rsp+928h+string], rcx
0x14001ccfe  test    ecx, ecx
0x14001cd00  jz      short loc_14001CD15
0x14001cd02  lea     rdx, [rsp+928h+string]
0x14001cd07  lea     rcx, [rsp+928h+var_8E0]
0x14001cd0c  call    sub_140015864
0x14001cd11  mov     ecx, [rsp+928h+var_8E8]
0x14001cd15  lea     rax, [rsp+928h+var_8E0]
0x14001cd1a  mov     [rsp+928h+var_8B8], rax
0x14001cd1f  mov     [rsp+928h+var_8B0], r15
0x14001cd24  mov     [rsp+928h+var_8A8], 1
0x14001cd2c  mov     r13d, esi
0x14001cd2f  test    ecx, ecx
0x14001cd31  jz      loc_14001CDDC
0x14001cd37  mov     [rsp+928h+string], rsi
0x14001cd3c  mov     rdi, [rsp+928h+var_900]
0x14001cd41  mov     rax, [rdi]
0x14001cd44  mov     rbx, [rax+30h]
0x14001cd48  xor     ecx, ecx; string
0x14001cd4a  call    cs:WindowsDeleteString
0x14001cd50  mov     [rsp+928h+string], rsi
0x14001cd55  lea     r8, [rsp+928h+string]
0x14001cd5a  mov     edx, r13d
0x14001cd5d  mov     rcx, rdi
0x14001cd60  mov     rax, rbx
0x14001cd63  call    sub_1400CA010
0x14001cd68  mov     [rsp+928h+var_908], eax
0x14001cd6c  test    eax, eax
0x14001cd6e  js      loc_14001D00A
0x14001cd74  mov     rdx, [rsp+928h+string]
0x14001cd79  mov     rcx, [r15+88h]
0x14001cd80  call    sub_1400533EC
0x14001cd85  test    eax, eax
0x14001cd87  js      loc_14001CF62
0x14001cd8d  mov     rax, [rsp+928h+string]
0x14001cd92  mov     [rsp+928h+lpCriticalSection], rax
0x14001cd97  mov     rdx, qword ptr [rsp+928h+var_8E0+8]
0x14001cd9c  cmp     rdx, [rsp+928h+var_8D0]
0x14001cda1  jz      short loc_14001CDAE
0x14001cda3  mov     [rdx], rax
0x14001cda6  add     qword ptr [rsp+928h+var_8E0+8], 8
0x14001cdac  jmp     short loc_14001CDBE
0x14001cdae  lea     r8, [rsp+928h+lpCriticalSection]
0x14001cdb3  lea     rcx, [rsp+928h+var_8E0]
0x14001cdb8  call    sub_140015640
0x14001cdbd  nop
0x14001cdbe  mov     rcx, [rsp+928h+string]; string
0x14001cdc3  call    cs:WindowsDeleteString
0x14001cdc9  inc     r13d
0x14001cdcc  cmp     r13d, [rsp+928h+var_8E8]
0x14001cdd1  jb      loc_14001CD37
0x14001cdd7  mov     rbx, [rsp+928h+var_8C8]
0x14001cddc  mov     [rsp+928h+var_8A8], sil
0x14001cde4  mov     [rsp+928h+lpCriticalSection], r15
0x14001cde9  test    r15, r15
0x14001cdec  jz      short loc_14001CDFE
0x14001cdee  mov     rax, [r15]
0x14001cdf1  mov     rcx, r15
0x14001cdf4  mov     rax, [rax+8]
0x14001cdf8  call    sub_1400CA010
0x14001cdfd  nop
0x14001cdfe  mov     [rsp+928h+string], r12
0x14001ce03  mov     rax, [r12]
0x14001ce07  mov     rcx, r12
0x14001ce0a  mov     rax, [rax+8]
0x14001ce0e  call    sub_1400CA010
0x14001ce13  nop
0x14001ce14  lock inc dword ptr [r15+0C4h]
0x14001ce1c  mov     [rsp+928h+var_8C8], r15
0x14001ce21  mov     [rsp+928h+var_8C0], 1
0x14001ce26  test    r15, r15
0x14001ce29  jz      short loc_14001CE3B
0x14001ce2b  mov     rax, [r15]
0x14001ce2e  mov     rcx, r15
0x14001ce31  mov     rax, [rax+8]
0x14001ce35  call    sub_1400CA010
0x14001ce3a  nop
0x14001ce3b  mov     [rsp+928h+var_890], r15
0x14001ce43  mov     [rsp+928h+var_888], rbx
0x14001ce4b  mov     rax, [r12]
0x14001ce4f  mov     rcx, r12
0x14001ce52  mov     rax, [rax+8]
0x14001ce56  call    sub_1400CA010
0x14001ce5b  nop
0x14001ce5c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_dcde832d9f7d587edd7fd97a859e7fc3_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_dcde832d9f7d587edd7fd97a859e7fc3_,void,>::`vftable'
0x14001ce63  mov     [rsp+928h+var_878], rax
0x14001ce6b  mov     [rsp+928h+var_870], r15
0x14001ce73  mov     [rsp+928h+var_898], rsi
0x14001ce7b  mov     [rsp+928h+var_868], r15
0x14001ce83  mov     [rsp+928h+var_860], rbx
0x14001ce8b  mov     [rsp+928h+var_858], r12
0x14001ce93  mov     [rsp+928h+var_880], rsi
0x14001ce9b  lea     rax, [rsp+928h+var_878]
0x14001cea3  mov     [rsp+928h+var_840], rax
0x14001ceab  lea     rcx, [rsp+928h+var_878]
0x14001ceb3  call    sub_14001D480
0x14001ceb8  mov     [rsp+928h+var_908], eax
0x14001cebc  mov     rcx, [rsp+928h+var_840]
0x14001cec4  test    rcx, rcx
0x14001cec7  jz      short loc_14001CEE7
0x14001cec9  mov     rax, [rcx]
0x14001cecc  lea     rdx, [rsp+928h+var_878]
0x14001ced4  cmp     rcx, rdx
0x14001ced7  setnz   dl
0x14001ceda  mov     rax, [rax+20h]
0x14001cede  call    sub_1400CA010
0x14001cee3  mov     eax, [rsp+928h+var_908]
0x14001cee7  test    eax, eax
0x14001cee9  jns     loc_14001D071
0x14001ceef  lea     rax, [rsp+928h+var_908]
0x14001cef4  mov     [rsp+928h+var_8C8], rax
0x14001cef9  lea     rcx, [rsp+928h+var_8C8]
0x14001cefe  call    sub_140017F80
0x14001cf03  mov     ebx, [rsp+928h+var_908]
0x14001cf07  mov     rcx, r15
0x14001cf0a  call    sub_14001FAB4
0x14001cf0f  nop
0x14001cf10  mov     rax, [r12]
0x14001cf14  mov     rcx, r12
0x14001cf17  mov     rax, [rax+10h]
0x14001cf1b  call    sub_1400CA010
0x14001cf20  nop
0x14001cf21  test    r15, r15
0x14001cf24  jz      short loc_14001CF36
0x14001cf26  mov     rax, [r15]
0x14001cf29  mov     rcx, r15
0x14001cf2c  mov     rax, [rax+10h]
0x14001cf30  call    sub_1400CA010
0x14001cf35  nop
0x14001cf36  lea     rcx, [rsp+928h+var_8E0]
0x14001cf3b  call    sub_140019AA0
0x14001cf40  nop
0x14001cf41  mov     rcx, [rsp+928h+var_900]
0x14001cf46  test    rcx, rcx
0x14001cf49  jz      short loc_14001CF5D
0x14001cf4b  mov     [rsp+928h+var_900], rsi
0x14001cf50  mov     rax, [rcx]
0x14001cf53  mov     rax, [rax+10h]
0x14001cf57  call    sub_1400CA010
0x14001cf5c  nop
0x14001cf5d  jmp     loc_14001CC75
0x14001cf62  lea     rax, [rsp+928h+string]
0x14001cf67  mov     [rsp+928h+lpCriticalSection], rax
0x14001cf6c  mov     [rsp+928h+var_838], si
0x14001cf74  xor     edx, edx; Val
0x14001cf76  mov     r8d, 7FEh; Size
0x14001cf7c  lea     rcx, [rsp+928h+var_836]; void *
0x14001cf84  call    memset
0x14001cf89  lea     rdx, [rsp+928h+var_838]
0x14001cf91  lea     rcx, [rsp+928h+lpCriticalSection]
0x14001cf96  call    sub_14001B090
0x14001cf9b  mov     [rsp+928h+var_908], 80070057h
0x14001cfa3  lea     rax, [rsp+928h+var_908]
0x14001cfa8  mov     [rsp+928h+lpCriticalSection], rax
0x14001cfad  lea     rcx, [rsp+928h+lpCriticalSection]
0x14001cfb2  call    sub_140018E8C
0x14001cfb7  mov     ebx, [rsp+928h+var_908]
0x14001cfbb  mov     rcx, [rsp+928h+string]; string
0x14001cfc0  call    cs:WindowsDeleteString
0x14001cfc6  mov     [rsp+928h+string], rsi
0x14001cfcb  mov     [rsp+928h+var_8A8], sil
0x14001cfd3  lea     rcx, [rsp+928h+var_8B8]
0x14001cfd8  call    sub_14001B698
0x14001cfdd  nop
0x14001cfde  lea     rcx, [rsp+928h+var_8E0]
0x14001cfe3  call    sub_140019AA0
0x14001cfe8  nop
0x14001cfe9  mov     rcx, [rsp+928h+var_900]
0x14001cfee  test    rcx, rcx
0x14001cff1  jz      short loc_14001D005
0x14001cff3  mov     [rsp+928h+var_900], rsi
0x14001cff8  mov     rax, [rcx]
0x14001cffb  mov     rax, [rax+10h]
0x14001cfff  call    sub_1400CA010
0x14001d004  nop
0x14001d005  jmp     loc_14001CC75
0x14001d00a  lea     rax, [rsp+928h+var_908]
0x14001d00f  mov     [rsp+928h+lpCriticalSection], rax
0x14001d014  lea     rcx, [rsp+928h+lpCriticalSection]
0x14001d019  call    sub_14001790C
0x14001d01e  mov     ebx, [rsp+928h+var_908]
0x14001d022  mov     rcx, [rsp+928h+string]; string
0x14001d027  call    cs:WindowsDeleteString
0x14001d02d  mov     [rsp+928h+string], rsi
0x14001d032  mov     [rsp+928h+var_8A8], sil
0x14001d03a  lea     rcx, [rsp+928h+var_8B8]
0x14001d03f  call    sub_14001B698
0x14001d044  nop
0x14001d045  lea     rcx, [rsp+928h+var_8E0]
0x14001d04a  call    sub_140019AA0
0x14001d04f  nop
0x14001d050  mov     rcx, [rsp+928h+var_900]
0x14001d055  test    rcx, rcx
0x14001d058  jz      short loc_14001D06C
0x14001d05a  mov     [rsp+928h+var_900], rsi
0x14001d05f  mov     rax, [rcx]
0x14001d062  mov     rax, [rax+10h]
0x14001d066  call    sub_1400CA010
0x14001d06b  nop
0x14001d06c  jmp     loc_14001CC75
0x14001d071  mov     rax, [r12]
0x14001d075  mov     rcx, r12
0x14001d078  mov     rax, [rax+10h]
0x14001d07c  call    sub_1400CA010
0x14001d081  nop
0x14001d082  test    r15, r15
0x14001d085  jz      short loc_14001D097
0x14001d087  mov     rax, [r15]
0x14001d08a  mov     rcx, r15
0x14001d08d  mov     rax, [rax+10h]
0x14001d091  call    sub_1400CA010
0x14001d096  nop
0x14001d097  lea     rcx, [rsp+928h+var_8E0]
0x14001d09c  call    sub_140019AA0
  ... truncated ...
```
