# sub_1402CEAB0

- ea: `0x1402ceab0`
- end: `0x1402cf002`
- name: `sub_1402CEAB0`
- size: `1362`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1402ce90c`
- `0x14072c208`

## callees

- `0x14001aa0c`
- `0x14001e270`
- `0x14001e4f4`
- `0x140020774`
- `0x140020a28`
- `0x140021ab8`
- `0x140024fa8`
- `0x140026ddc`
- `0x140026eb0`
- `0x140027db0`
- `0x140045380`
- `0x1401687e8`
- `0x140176448`
- `0x1402ceab0`
- `0x1403e1680`
- `0x1403e60fd`

## import_xrefs

- `KERNEL32!CompareStringEx` at `0x1402cec81`
- `KERNEL32!CompareStringEx` at `0x1402cecce`
- `KERNEL32!CompareStringEx` at `0x1402ced7d`
- `KERNEL32!CompareStringEx` at `0x1402cedca`
- `KERNEL32!CompareStringEx` at `0x1402cec81`
- `KERNEL32!CompareStringEx` at `0x1402cecce`
- `KERNEL32!CompareStringEx` at `0x1402ced7d`
- `KERNEL32!CompareStringEx` at `0x1402cedca`
- `KERNEL32!GetLastError` at `0x1402ceeab`
- `KERNEL32!GetLastError` at `0x1402ceeee`
- `KERNEL32!GetLastError` at `0x1402ceeab`
- `KERNEL32!GetLastError` at `0x1402ceeee`

## string_xrefs

- `0x1402cef3c`: `EnforcedUpdateDialogDeadlineReached`
- `0x1402cef66`: `EnforcedUpdateDialogUserAccepts`
- `0x1402cef90`: `EnforcedUpdateToast`

## pseudocode

```c
_QWORD *__fastcall sub_1402CEAB0(__int64 a1, _QWORD *a2, char a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __m128i si128; // xmm0
  LPCWCH v11; // rsi
  LPCWCH v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // r15
  __int64 v15; // r14
  int cchCount2; // ebx
  int v17; // eax
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  LPCWCH *v21; // rsi
  int v22; // ebx
  int v23; // eax
  int v24; // eax
  int v25; // ebx
  int v26; // eax
  int v27; // eax
  wchar_t *v28; // rdx
  void *v29; // rcx
  DWORD v31; // eax
  DWORD LastError; // eax
  int v33; // eax
  __int64 v34; // rax
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+54h] [rbp-ACh]
  std::_Ref_count_base *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v38[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v39; // [rsp+78h] [rbp-88h]
  int pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int16 v41; // [rsp+84h] [rbp-7Ch]
  DWORD v42; // [rsp+284h] [rbp+184h]
  __int16 v43; // [rsp+288h] [rbp+188h]
  __int16 v44; // [rsp+388h] [rbp+288h]
  int v45; // [rsp+408h] [rbp+308h]
  LPCWCH lpString1[2]; // [rsp+410h] [rbp+310h] BYREF
  __m128i v47; // [rsp+420h] [rbp+320h]
  WCHAR String1[12]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int64 v49; // [rsp+448h] [rbp+348h]
  _QWORD v50[4]; // [rsp+450h] [rbp+350h] BYREF

  v39 = a2;
  v36 = 0;
  sub_140021AB8((__int64)String1, L"UNDEFINED");
  v6 = sub_140027DB0(a1, v38);
  v7 = *(_QWORD *)sub_140026EB0(*v6, v37);
  v35 = 21;
  sub_140026DDC(v7, &v35, String1);
  if ( v37[1] )
    sub_14001E4F4(v37[1]);
  *(__m128i *)v37 = _mm_load_si128((const __m128i *)&xmmword_14084AF40);
  if ( v38[1] )
    sub_14001E4F4(v38[1]);
  v8 = sub_140027DB0(a1, v38);
  v9 = *(_QWORD *)sub_140026EB0(*v8, v37);
  v35 = 9;
  sub_140024FA8(v9, lpString1, &v35);
  if ( v37[1] )
    sub_14001E4F4(v37[1]);
  si128 = _mm_load_si128((const __m128i *)&xmmword_14084AF40);
  *(__m128i *)v37 = si128;
  if ( v38[1] )
  {
    sub_14001E4F4(v38[1]);
    si128 = _mm_load_si128((const __m128i *)&xmmword_14084AF40);
  }
  *(__m128i *)v38 = si128;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v36 = 1;
  v11 = (LPCWCH)lpString1;
  v12 = lpString1[0];
  v13 = v47.m128i_u64[1];
  if ( v47.m128i_i64[1] > 7uLL )
    v11 = lpString1[0];
  v14 = -1;
  if ( !v11 || !*v11 )
  {
LABEL_19:
    v21 = lpString1;
    if ( v13 > 7 )
      v21 = (LPCWCH *)v12;
    if ( v21 && *(_WORD *)v21 )
    {
      if ( !aCom[0] )
        goto LABEL_39;
      do
        ++v14;
      while ( *((_WORD *)v21 + v14) );
      v22 = sub_140020A28(3);
      v23 = sub_140020A28(v14);
      v24 = CompareStringEx(&LocaleName, 1u, (LPCWCH)v21, v23, L"COM", v22, 0, 0, 0);
      if ( !v24 )
      {
        v25 = sub_140020A28(3);
        v26 = sub_140020A28(v14);
        v24 = CompareStringEx(L"en-US", 1u, (LPCWCH)v21, v26, L"COM", v25, 0, 0, 0);
        if ( !v24 )
        {
          LastError = GetLastError();
          pExceptionObject = 15;
          v42 = LastError;
          v45 = 808464432;
          v44 = 0;
          v43 = 0;
          v41 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      v27 = v24 - 2;
    }
    else
    {
      if ( aCom[0] )
        goto LABEL_39;
      v27 = 0;
    }
    if ( !v27 )
    {
      v28 = (wchar_t *)L"COM";
LABEL_30:
      v29 = a2;
      goto LABEL_31;
    }
LABEL_39:
    v28 = L"Default";
    goto LABEL_30;
  }
  v15 = -1;
  do
    ++v15;
  while ( v11[v15] );
  cchCount2 = sub_140020A28(4);
  v17 = sub_140020A28(v15);
  v18 = CompareStringEx(&LocaleName, 1u, v11, v17, L"User", cchCount2, 0, 0, 0);
  if ( !v18 )
  {
    v19 = sub_140020A28(4);
    v20 = sub_140020A28(v15);
    v18 = CompareStringEx(L"en-US", 1u, v11, v20, L"User", v19, 0, 0, 0);
    if ( !v18 )
    {
      v31 = GetLastError();
      pExceptionObject = 15;
      v42 = v31;
      v45 = 808464432;
      v44 = 0;
      v43 = 0;
      v41 = 0;
      throw (OException *)&pExceptionObject;
    }
  }
  if ( v18 != 2 )
  {
    v13 = v47.m128i_u64[1];
    v12 = lpString1[0];
    goto LABEL_19;
  }
  if ( !(unsigned int)sub_1401687E8(String1, L"EnforcedUpdateDialogDeadlineReached") )
  {
    v28 = L"UserDeadline";
    goto LABEL_30;
  }
  if ( !(unsigned int)sub_1401687E8(String1, L"EnforcedUpdateDialogUserAccepts") )
  {
    v28 = L"UserAccepts";
    goto LABEL_30;
  }
  v33 = sub_1401687E8(String1, L"EnforcedUpdateToast");
  v29 = a2;
  if ( v33 )
    v28 = (wchar_t *)L"User";
  else
    v28 = L"UserToast";
LABEL_31:
  sub_140020774(v29, v28);
  if ( a3 )
  {
    v34 = sub_140176448(v50, L"%s%s", a2, off_140BE7278);
    sub_14001AA0C(a2, v34);
    sub_140045380(v50);
  }
  if ( v47.m128i_i64[1] > 7uLL )
    sub_14001E270((_QWORD *)lpString1[0], 2 * v47.m128i_i64[1] + 2);
  lpString1[0] = (LPCWCH)19937;
  v47 = _mm_load_si128((const __m128i *)&xmmword_14082E580);
  if ( v49 > 7 )
    sub_14001E270(*(_QWORD **)String1, 2 * v49 + 2);
  return a2;
}

```

## disassembly

```asm
0x1402ceab0  mov     [rsp-8+arg_10], rbx
0x1402ceab5  push    rbp
0x1402ceab6  push    rsi
0x1402ceab7  push    rdi
0x1402ceab8  push    r12
0x1402ceaba  push    r13
0x1402ceabc  push    r14
0x1402ceabe  push    r15
0x1402ceac0  lea     rbp, [rsp-380h]
0x1402ceac8  sub     rsp, 480h
0x1402ceacf  mov     rax, cs:__security_cookie
0x1402cead6  xor     rax, rsp
0x1402cead9  mov     [rbp+3B0h+var_40], rax
0x1402ceae0  mov     r12b, r8b
0x1402ceae3  mov     rdi, rdx
0x1402ceae6  mov     rbx, rcx
0x1402ceae9  mov     [rsp+4B0h+var_438], rdx
0x1402ceaee  xor     r13d, r13d
0x1402ceaf1  mov     [rsp+4B0h+var_45C], r13d
0x1402ceaf6  lea     rdx, aUndefined; "UNDEFINED"
0x1402ceafd  lea     rcx, [rbp+3B0h+String1]
0x1402ceb04  call    sub_140021AB8
0x1402ceb09  lea     rdx, [rsp+4B0h+var_448]
0x1402ceb0e  mov     rcx, rbx
0x1402ceb11  call    sub_140027DB0
0x1402ceb16  lea     rdx, [rsp+4B0h+var_458]
0x1402ceb1b  mov     rcx, [rax]
0x1402ceb1e  xchg    ax, ax
0x1402ceb20  call    sub_140026EB0
0x1402ceb25  mov     rcx, [rax]
0x1402ceb28  mov     [rsp+4B0h+var_460], 15h
0x1402ceb30  lea     r8, [rbp+3B0h+String1]
0x1402ceb37  lea     rdx, [rsp+4B0h+var_460]
0x1402ceb3c  call    sub_140026DDC
0x1402ceb41  mov     rcx, [rsp+4B0h+var_458+8]; this
0x1402ceb46  test    rcx, rcx
0x1402ceb49  jz      short loc_1402CEB50
0x1402ceb4b  call    sub_14001E4F4
0x1402ceb50  movdqa  xmm0, cs:xmmword_14084AF40
0x1402ceb58  movdqu  xmmword ptr [rsp+4B0h+var_458], xmm0
0x1402ceb5e  mov     rcx, [rsp+4B0h+var_448+8]; this
0x1402ceb63  test    rcx, rcx
0x1402ceb66  jz      short loc_1402CEB6D
0x1402ceb68  call    sub_14001E4F4
0x1402ceb6d  lea     rdx, [rsp+4B0h+var_448]
0x1402ceb72  mov     rcx, rbx
0x1402ceb75  call    sub_140027DB0
0x1402ceb7a  lea     rdx, [rsp+4B0h+var_458]
0x1402ceb7f  mov     rcx, [rax]
0x1402ceb82  call    sub_140026EB0
0x1402ceb87  mov     rcx, [rax]
0x1402ceb8a  mov     [rsp+4B0h+var_460], 9
0x1402ceb92  lea     r8, [rsp+4B0h+var_460]
0x1402ceb97  lea     rdx, [rbp+3B0h+lpString1]
0x1402ceb9e  call    sub_140024FA8
0x1402ceba3  mov     rcx, [rsp+4B0h+var_458+8]; this
0x1402ceba8  test    rcx, rcx
0x1402cebab  jz      short loc_1402CEBB2
0x1402cebad  call    sub_14001E4F4
0x1402cebb2  movdqa  xmm0, cs:xmmword_14084AF40
0x1402cebba  movdqu  xmmword ptr [rsp+4B0h+var_458], xmm0
0x1402cebc0  mov     rcx, [rsp+4B0h+var_448+8]; this
0x1402cebc5  test    rcx, rcx
0x1402cebc8  jz      short loc_1402CEBD7
0x1402cebca  call    sub_14001E4F4
0x1402cebcf  movdqa  xmm0, cs:xmmword_14084AF40
0x1402cebd7  movdqu  xmmword ptr [rsp+4B0h+var_448], xmm0
0x1402cebdd  xorps   xmm0, xmm0
0x1402cebe0  movups  xmmword ptr [rdi], xmm0
0x1402cebe3  mov     [rdi+10h], r13
0x1402cebe7  mov     qword ptr [rdi+18h], 7
0x1402cebef  mov     [rdi], r13w
0x1402cebf3  mov     [rsp+4B0h+var_45C], 1
0x1402cebfb  lea     rsi, [rbp+3B0h+lpString1]
0x1402cec02  mov     rax, [rbp+3B0h+lpString1]
0x1402cec09  mov     rcx, [rbp+3B0h+var_88]
0x1402cec10  cmp     rcx, 7
0x1402cec14  cmova   rsi, rax
0x1402cec18  or      r15, 0FFFFFFFFFFFFFFFFh
0x1402cec1c  test    rsi, rsi
0x1402cec1f  jz      loc_1402CECF3
0x1402cec25  cmp     r13w, [rsi]
0x1402cec29  jz      loc_1402CECF3
0x1402cec2f  mov     r14, r15
0x1402cec32  inc     r14
0x1402cec35  cmp     [rsi+r14*2], r13w
0x1402cec3a  jnz     short loc_1402CEC32
0x1402cec3c  mov     ecx, 4
0x1402cec41  call    sub_140020A28
0x1402cec46  mov     ebx, eax
0x1402cec48  mov     rcx, r14
0x1402cec4b  call    sub_140020A28
0x1402cec50  mov     [rsp+4B0h+lParam], r13; lParam
0x1402cec55  mov     [rsp+4B0h+lpReserved], r13; lpReserved
0x1402cec5a  mov     [rsp+4B0h+lpVersionInformation], r13; lpVersionInformation
0x1402cec5f  mov     [rsp+4B0h+cchCount2], ebx; cchCount2
0x1402cec63  lea     rbx, aUser_2; "User"
0x1402cec6a  mov     [rsp+4B0h+lpString2], rbx; lpString2
0x1402cec6f  mov     r9d, eax; cchCount1
0x1402cec72  mov     r8, rsi; lpString1
0x1402cec75  mov     edx, 1; dwCmpFlags
0x1402cec7a  lea     rcx, LocaleName; lpLocaleName
0x1402cec81  call    cs:CompareStringEx
0x1402cec87  test    eax, eax
0x1402cec89  jnz     short loc_1402CECDC
0x1402cec8b  lea     ecx, [rax+4]
0x1402cec8e  call    sub_140020A28
0x1402cec93  mov     ebx, eax
0x1402cec95  mov     rcx, r14
0x1402cec98  call    sub_140020A28
0x1402cec9d  mov     [rsp+4B0h+lParam], r13; lParam
0x1402ceca2  mov     [rsp+4B0h+lpReserved], r13; lpReserved
0x1402ceca7  mov     [rsp+4B0h+lpVersionInformation], r13; lpVersionInformation
0x1402cecac  mov     [rsp+4B0h+cchCount2], ebx; cchCount2
0x1402cecb0  lea     rbx, aUser_2; "User"
0x1402cecb7  mov     [rsp+4B0h+lpString2], rbx; lpString2
0x1402cecbc  mov     r9d, eax; cchCount1
0x1402cecbf  mov     r8, rsi; lpString1
0x1402cecc2  mov     edx, 1; dwCmpFlags
0x1402cecc7  lea     rcx, aEnUs; "en-US"
0x1402cecce  call    cs:CompareStringEx
0x1402cecd4  test    eax, eax
0x1402cecd6  jz      loc_1402CEEAB
0x1402cecdc  add     eax, 0FFFFFFFEh
0x1402cecdf  jz      loc_1402CEF39
0x1402cece5  mov     rcx, [rbp+3B0h+var_88]
0x1402cecec  mov     rax, [rbp+3B0h+lpString1]
0x1402cecf3  lea     rsi, [rbp+3B0h+lpString1]
0x1402cecfa  cmp     rcx, 7
0x1402cecfe  cmova   rsi, rax
0x1402ced02  mov     r14d, 3
0x1402ced08  lea     rcx, aCom; "COM"
0x1402ced0f  test    rsi, rsi
0x1402ced12  jz      loc_1402CEE8B
0x1402ced18  cmp     r13w, [rsi]
0x1402ced1c  jz      loc_1402CEE8B
0x1402ced22  cmp     r13w, word ptr cs:aCom; "COM"
0x1402ced2a  jz      loc_1402CEE99
0x1402ced30  inc     r15
0x1402ced33  cmp     [rsi+r15*2], r13w
0x1402ced38  jnz     short loc_1402CED30
0x1402ced3a  mov     rcx, r14
0x1402ced3d  call    sub_140020A28
0x1402ced42  mov     ebx, eax
0x1402ced44  mov     rcx, r15
0x1402ced47  call    sub_140020A28
0x1402ced4c  mov     [rsp+4B0h+lParam], r13; lParam
0x1402ced51  mov     [rsp+4B0h+lpReserved], r13; lpReserved
0x1402ced56  mov     [rsp+4B0h+lpVersionInformation], r13; lpVersionInformation
0x1402ced5b  mov     [rsp+4B0h+cchCount2], ebx; cchCount2
0x1402ced5f  lea     rdx, aCom; "COM"
0x1402ced66  mov     [rsp+4B0h+lpString2], rdx; lpString2
0x1402ced6b  mov     r9d, eax; cchCount1
0x1402ced6e  mov     r8, rsi; lpString1
0x1402ced71  mov     edx, 1; dwCmpFlags
0x1402ced76  lea     rcx, LocaleName; lpLocaleName
0x1402ced7d  call    cs:CompareStringEx
0x1402ced83  test    eax, eax
0x1402ced85  jnz     short loc_1402CEDD8
0x1402ced87  mov     rcx, r14
0x1402ced8a  call    sub_140020A28
0x1402ced8f  mov     ebx, eax
0x1402ced91  mov     rcx, r15
0x1402ced94  call    sub_140020A28
0x1402ced99  mov     [rsp+4B0h+lParam], r13; lParam
0x1402ced9e  mov     [rsp+4B0h+lpReserved], r13; lpReserved
0x1402ceda3  mov     [rsp+4B0h+lpVersionInformation], r13; lpVersionInformation
0x1402ceda8  mov     [rsp+4B0h+cchCount2], ebx; cchCount2
0x1402cedac  lea     rcx, aCom; "COM"
0x1402cedb3  mov     [rsp+4B0h+lpString2], rcx; lpString2
0x1402cedb8  mov     r9d, eax; cchCount1
0x1402cedbb  mov     r8, rsi; lpString1
0x1402cedbe  mov     edx, 1; dwCmpFlags
0x1402cedc3  lea     rcx, aEnUs; "en-US"
0x1402cedca  call    cs:CompareStringEx
0x1402cedd0  test    eax, eax
0x1402cedd2  jz      loc_1402CEEEE
0x1402cedd8  add     eax, 0FFFFFFFEh
0x1402ceddb  lea     rcx, aCom; "COM"
0x1402cede2  test    eax, eax
0x1402cede4  jnz     loc_1402CEE99
0x1402cedea  mov     r8, r14
0x1402ceded  mov     rdx, rcx; Src
0x1402cedf0  mov     rcx, rdi; void *
0x1402cedf3  call    sub_140020774
0x1402cedf8  test    r12b, r12b
0x1402cedfb  jnz     loc_1402CEFC8
0x1402cee01  mov     rdx, [rbp+3B0h+var_88]
0x1402cee08  cmp     rdx, 7
0x1402cee0c  jbe     short loc_1402CEE22
0x1402cee0e  lea     rdx, ds:2[rdx*2]
0x1402cee16  mov     rcx, [rbp+3B0h+lpString1]
0x1402cee1d  call    sub_14001E270
0x1402cee22  mov     [rbp+3B0h+lpString1], 4DE1h
0x1402cee2d  movdqa  xmm0, cs:xmmword_14082E580
0x1402cee35  movdqu  xmmword ptr [rbp+320h], xmm0
0x1402cee3d  mov     rdx, [rbp+3B0h+var_68]
0x1402cee44  cmp     rdx, 7
0x1402cee48  jbe     short loc_1402CEE5E
0x1402cee4a  lea     rdx, ds:2[rdx*2]
0x1402cee52  mov     rcx, qword ptr [rbp+3B0h+String1]
0x1402cee59  call    sub_14001E270
0x1402cee5e  mov     rax, rdi
0x1402cee61  mov     rcx, [rbp+3B0h+var_40]
0x1402cee68  xor     rcx, rsp; StackCookie
0x1402cee6b  call    __security_check_cookie
0x1402cee70  mov     rbx, [rsp+4B0h+arg_10]
0x1402cee78  add     rsp, 480h
0x1402cee7f  pop     r15
0x1402cee81  pop     r14
0x1402cee83  pop     r13
0x1402cee85  pop     r12
0x1402cee87  pop     rdi
0x1402cee88  pop     rsi
0x1402cee89  pop     rbp
0x1402cee8a  retn
0x1402cee8b  cmp     r13w, word ptr cs:aCom; "COM"
0x1402cee93  jz      loc_1402CEF31
0x1402cee99  mov     r8d, 7
0x1402cee9f  lea     rdx, aDefault; "Default"
0x1402ceea6  jmp     loc_1402CEDF0
0x1402ceeab  call    cs:__imp_GetLastError
0x1402ceeb1  mov     [rbp+3B0h+pExceptionObject], 0Fh
0x1402ceeb8  mov     [rbp+3B0h+var_22C], eax
0x1402ceebe  mov     [rbp+3B0h+var_A8], 30303030h
0x1402ceec8  mov     [rbp+3B0h+var_128], r13w
0x1402ceed0  mov     [rbp+3B0h+var_228], r13w
0x1402ceed8  mov     [rbp+3B0h+var_42C], r13w
0x1402ceedd  lea     rdx, __TI2?AVOException@@; pThrowInfo
0x1402ceee4  lea     rcx, [rbp+3B0h+pExceptionObject]; pExceptionObject
0x1402ceee8  call    _CxxThrowException
0x1402ceeee  call    cs:__imp_GetLastError
0x1402ceef4  mov     [rbp+3B0h+pExceptionObject], 0Fh
0x1402ceefb  mov     [rbp+3B0h+var_22C], eax
0x1402cef01  mov     [rbp+3B0h+var_A8], 30303030h
0x1402cef0b  mov     [rbp+3B0h+var_128], r13w
0x1402cef13  mov     [rbp+3B0h+var_228], r13w
0x1402cef1b  mov     [rbp+3B0h+var_42C], r13w
0x1402cef20  lea     rdx, __TI2?AVOException@@; pThrowInfo
0x1402cef27  lea     rcx, [rbp+3B0h+pExceptionObject]; pExceptionObject
0x1402cef2b  call    _CxxThrowException
0x1402cef31  mov     eax, r13d
0x1402cef34  jmp     loc_1402CEDE2
0x1402cef39  xor     r8d, r8d
0x1402cef3c  lea     rdx, aEnforcedupdate; "EnforcedUpdateDialogDeadlineReached"
0x1402cef43  lea     rcx, [rbp+3B0h+String1]; lpString1
0x1402cef4a  call    sub_1401687E8
0x1402cef4f  test    eax, eax
0x1402cef51  jnz     short loc_1402CEF63
0x1402cef53  lea     r8d, [rax+0Ch]
0x1402cef57  lea     rdx, aUserdeadline; "UserDeadline"
0x1402cef5e  jmp     loc_1402CEDF0
0x1402cef63  xor     r8d, r8d
0x1402cef66  lea     rdx, aEnforcedupdate_0; "EnforcedUpdateDialogUserAccepts"
0x1402cef6d  lea     rcx, [rbp+3B0h+String1]; lpString1
0x1402cef74  call    sub_1401687E8
0x1402cef79  test    eax, eax
0x1402cef7b  jnz     short loc_1402CEF8D
0x1402cef7d  lea     r8d, [rax+0Bh]
0x1402cef81  lea     rdx, aUseraccepts; "UserAccepts"
0x1402cef88  jmp     loc_1402CEDF0
0x1402cef8d  xor     r8d, r8d
0x1402cef90  lea     rdx, aEnforcedupdate_1; "EnforcedUpdateToast"
0x1402cef97  lea     rcx, [rbp+3B0h+String1]; lpString1
0x1402cef9e  call    sub_1401687E8
0x1402cefa3  mov     rcx, rdi
0x1402cefa6  test    eax, eax
0x1402cefa8  jnz     short loc_1402CEFBA
0x1402cefaa  lea     r8d, [rax+9]
0x1402cefae  lea     rdx, aUsertoast; "UserToast"
0x1402cefb5  jmp     loc_1402CEDF3
0x1402cefba  mov     r8d, 4
0x1402cefc0  mov     rdx, rbx
0x1402cefc3  jmp     loc_1402CEDF3
0x1402cefc8  lea     r9, off_140BE7278; "CustomVersion"
0x1402cefcf  mov     r8, rdi
0x1402cefd2  lea     rdx, aSS; "%s%s"
0x1402cefd9  lea     rcx, [rbp+3B0h+var_60]
0x1402cefe0  call    sub_140176448
0x1402cefe5  mov     rdx, rax
0x1402cefe8  mov     rcx, rdi
0x1402cefeb  call    sub_14001AA0C
0x1402ceff0  lea     rcx, [rbp+3B0h+var_60]; void *
0x1402ceff7  call    sub_140045380
0x1402ceffc  jmp     loc_1402CEE01
```
