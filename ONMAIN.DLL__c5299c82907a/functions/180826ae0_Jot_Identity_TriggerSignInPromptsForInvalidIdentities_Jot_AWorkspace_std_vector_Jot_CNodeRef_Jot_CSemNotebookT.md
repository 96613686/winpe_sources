# Jot::Identity::TriggerSignInPromptsForInvalidIdentities(Jot::AWorkspace &,std::vector<Jot::CNodeRef<Jot::CSemNotebookTrait>,std::allocator<Jot::CNodeRef<Jot::CSemNotebookTrait>>> const &)

- ea: `0x180826ae0`
- end: `0x180826ff8`
- name: `?TriggerSignInPromptsForInvalidIdentities@Identity@Jot@@YAXAEAUAWorkspace@2@AEBV?$vector@V?$CNodeRef@VCSemNotebookTrait@Jot@@@Jot@@V?$allocator@V?$CNodeRef@VCSemNotebookTrait@Jot@@@Jot@@@std@@@std@@@Z`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a1660`

## callees

- `0x18002f2a0`
- `0x18002f61c`
- `0x18004ad1c`
- `0x180071198`
- `0x180091d40`
- `0x1800920a0`
- `0x1800a4464`
- `0x1800b3b78`
- `0x180111890`
- `0x18012b98c`
- `0x180269f54`
- `0x18029aad0`
- `0x1802de200`
- `0x1802de3a0`
- `0x18058b800`
- `0x1805b1410`
- `0x180826ae0`
- `0x180827000`
- `0x18082ae54`
- `0x1808395a4`
- `0x180ac6580`
- `0x180ac65b4`
- `0x180ac6af0`
- `0x180ac6e2c`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x180826bb5`
- `KERNEL32!SystemTimeToFileTime` at `0x180826bd2`
- `KERNEL32!SystemTimeToFileTime` at `0x180826bb5`
- `KERNEL32!SystemTimeToFileTime` at `0x180826bd2`
- `KERNEL32!FileTimeToSystemTime` at `0x180826b6d`
- `KERNEL32!FileTimeToSystemTime` at `0x180826b9d`
- `KERNEL32!FileTimeToSystemTime` at `0x180826b6d`
- `KERNEL32!FileTimeToSystemTime` at `0x180826b9d`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180826cde`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180826cde`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180826db0`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180826db0`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180826d24`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180826d6d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180826d24`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180826d6d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180826fca`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180826fca`
- `Mso20Win32Client!Mso20Win32Client_48723` at `0x180826c29`
- `Mso20Win32Client!Mso20Win32Client_48723` at `0x180826c29`

## string_xrefs

- `0x180826ddb`: `fHasIdentity`

## pseudocode

```c
void __fastcall Jot::Identity::TriggerSignInPromptsForInvalidIdentities(Jot *a1, __int64 *a2)
{
  struct Jot::CRegistryCache *v4; // rax
  unsigned int v5; // eax
  __int64 v6; // rbx
  struct _FILETIME v7; // rbx
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // r14
  __m128i si128; // xmm6
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 Tag; // rax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // r8
  FILETIME v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  Jot *v30; // rcx
  char *v31; // rdi
  void (__fastcall *v32)(char *, _QWORD); // rbx
  unsigned int v33; // eax
  void *v34; // rcx
  FILETIME FileTime; // [rsp+28h] [rbp-99h] BYREF
  __int64 v36; // [rsp+30h] [rbp-91h] BYREF
  struct _FILETIME v37; // [rsp+38h] [rbp-89h] BYREF
  unsigned __int64 v38; // [rsp+40h] [rbp-81h] BYREF
  _QWORD v39[2]; // [rsp+48h] [rbp-79h] BYREF
  __m128i v40; // [rsp+58h] [rbp-69h] BYREF
  __int128 v41; // [rsp+68h] [rbp-59h] BYREF
  __int64 v42; // [rsp+78h] [rbp-49h]
  unsigned __int64 *v43; // [rsp+80h] [rbp-41h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-39h] BYREF
  SYSTEMTIME v45; // [rsp+98h] [rbp-29h] BYREF
  __int64 (__fastcall **v46)(); // [rsp+A8h] [rbp-19h] BYREF
  __int64 (__fastcall **v47)(); // [rsp+B0h] [rbp-11h]
  const wchar_t *v48; // [rsp+B8h] [rbp-9h]
  __int64 v49; // [rsp+C0h] [rbp-1h]
  __int64 *v50; // [rsp+C8h] [rbp+7h]
  __int16 v51; // [rsp+D0h] [rbp+Fh]

  v4 = Jot::UseRegistryCache(a1);
  v5 = (**((__int64 (__fastcall ***)(__int64))v4 + 201))((__int64)v4 + 1608);
  v6 = v5;
  if ( !v5 )
    goto LABEL_11;
  v37 = (struct _FILETIME)(10000000 * ((unsigned int)sub_1800A4464() + 0x2C8DF3700LL));
  FileTime = v37;
  FileTimeToSystemTime(&FileTime, &SystemTime);
  v37 = (struct _FILETIME)(10000000 * (v6 + 0x2C8DF3700LL));
  FileTime = v37;
  FileTimeToSystemTime(&FileTime, &v45);
  v37 = 0;
  SystemTimeToFileTime(&SystemTime, &v37);
  v7 = v37;
  FileTime = 0;
  SystemTimeToFileTime(&v45, &FileTime);
  if ( *(_QWORD *)&v7 <= *(unsigned __int64 *)&FileTime )
    v8 = *(_QWORD *)&FileTime - *(_QWORD *)&v7;
  else
    v8 = *(_QWORD *)&v7 - *(_QWORD *)&FileTime;
  FileTime = (FILETIME)(v8 / 0x23C34600);
  v9 = v8 / 0x23C3460000000000LL;
  v10 = v8 / 0x23C34600;
  if ( (_DWORD)v9 )
    v10 = -1;
  v11 = sub_180827000();
  v12 = (_QWORD *)(*(_BYTE *)(v11 + 2) ? v11 + 96 : Mso20Win32Client_48723(v11));
  if ( 60LL * *v12 <= v10 )
  {
LABEL_11:
    v39[0] = 0;
    v41 = 0;
    v42 = 0;
    v13 = *a2;
    v14 = a2[1];
    if ( *a2 != v14 )
    {
      si128 = _mm_load_si128((const __m128i *)&xmmword_1810DD7D0);
      do
      {
        if ( !(unsigned __int8)sub_180111890(v13) )
        {
          v16 = sub_180091D40(&FileTime, v13);
          sub_18012B98C(&v37, v16);
          v17 = sub_180091D40(&v38, v13);
          v18 = sub_1800B3B78(v17, 0, 0);
          if ( v37 )
          {
            sub_18082AE54(&v40, *(_QWORD *)&v37);
            if ( __ExceptionPtrToBool(&v40) )
            {
              Tag = Jot::GetTag(&v43, &v40);
              v20 = *(_BYTE *)(Tag + 4) ? *(_DWORD *)Tag : 0;
              if ( v20 != 17586119 )
              {
                ++v39[0];
                v45 = 0;
                __ExceptionPtrCopy(&v45, &v40);
                v21 = sub_180AC6AF0(&v46, v13, &v45);
                v22 = v21;
                v23 = *((_QWORD *)&v41 + 1);
                if ( *((_QWORD *)&v41 + 1) == v42 )
                {
                  sub_180AC65B4(&v41, *((_QWORD *)&v41 + 1), v21);
                }
                else
                {
                  v39[1] = *((_QWORD *)&v41 + 1);
                  sub_180091D40(*((_QWORD *)&v41 + 1), v21);
                  *(_QWORD *)(v23 + 8) = 0;
                  *(_QWORD *)(v23 + 16) = 0;
                  __ExceptionPtrCopy((void *)(v23 + 8), (const void *)(v22 + 8));
                  sub_180269F54(v23 + 24, v22 + 24);
                  *((_QWORD *)&v41 + 1) += 56LL;
                }
                sub_180AC6E2C(&v46);
              }
            }
            __ExceptionPtrDestroy(&v40);
            v40 = si128;
          }
          else
          {
            LOBYTE(v36) = v18 != 0;
            v46 = off_18106B988;
            v47 = off_18109A188;
            v48 = L"fHasIdentity";
            v49 = -1;
            v50 = &v36;
            v51 = 4;
            *(_QWORD *)&SystemTime.wYear = &off_1810DD650;
            *(_QWORD *)&SystemTime.wHour = "SignInPromptsForInvalidIdentitiesSkippedNotebook";
            sub_180071198(508117977, &SystemTime, 50, &v46);
          }
          if ( v37 )
            (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v37 + 16LL))(v37);
        }
        v13 += 8;
      }
      while ( v13 != v14 );
    }
    v24 = *(_QWORD *)(*(__int64 (__fastcall **)(Jot *, FILETIME *))(*(_QWORD *)a1 + 856LL))(a1, &FileTime);
    v26 = FileTime;
    if ( FileTime )
    {
      FileTime = 0;
      (*(void (__fastcall **)(FILETIME))(**(_QWORD **)&v26 + 8LL))(v26);
    }
    if ( v24 )
    {
      LOBYTE(v25) = 1;
      sub_1808395A4(&v37, v24, v25);
      v43 = &v38;
      v27 = sub_18004AD1C(&v38, &v37);
      v28 = (*(__int64 (__fastcall **)(Jot *))(*(_QWORD *)a1 + 8LL))(a1);
      sub_1805B1410(v28, v27, &v41);
      if ( v37 )
        (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v37 + 8LL))(v37);
    }
    v46 = off_1810960B8;
    v47 = off_1810D3080;
    v48 = L"promptedNotebooks";
    v49 = -1;
    v50 = v39;
    v51 = 4;
    v29 = sub_18002F61C(&v43, 2);
    *(_QWORD *)&SystemTime.wYear = &off_1810DD650;
    *(_QWORD *)&SystemTime.wHour = "ForcePromptForNotebookCheckRan";
    sub_18002F2A0(&SystemTime, v29, &v46);
    v31 = (char *)Jot::UseRegistryCache(v30) + 1608;
    v32 = *(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v31 + 8LL);
    v33 = sub_1800A4464();
    v32(v31, v33);
    if ( (_QWORD)v41 )
    {
      sub_180AC6580(v41, *((_QWORD *)&v41 + 1));
      v34 = (void *)v41;
      v38 = 8 * ((v42 - (__int64)v41) >> 3);
      FileTime = (FILETIME)v41;
      if ( v38 >= 0x1000 )
      {
        sub_18058B800(&FileTime, &v38);
        v34 = (void *)FileTime;
      }
      free(v34);
    }
  }
}

```

## disassembly

```asm
0x180826ae0  mov     rax, rsp
0x180826ae3  mov     [rax+18h], rbx
0x180826ae7  push    rbp
0x180826ae8  push    rsi
0x180826ae9  push    rdi
0x180826aea  push    r14
0x180826aec  push    r15
0x180826aee  lea     rbp, [rax-5Fh]
0x180826af2  sub     rsp, 0F0h
0x180826af9  movaps  xmmword ptr [rax-38h], xmm6
0x180826afd  mov     rax, cs:__security_cookie
0x180826b04  xor     rax, rsp
0x180826b07  mov     [rbp+57h+var_38], rax
0x180826b0b  mov     rdi, rdx
0x180826b0e  mov     r15, rcx
0x180826b11  call    ?UseRegistryCache@Jot@@YAPEAVCRegistryCache@1@XZ; Jot::UseRegistryCache(void)
0x180826b16  lea     rcx, [rax+648h]
0x180826b1d  mov     rax, [rcx]
0x180826b20  mov     rax, [rax]
0x180826b23  call    cs:__guard_dispatch_icall_fptr
0x180826b29  mov     ebx, eax
0x180826b2b  test    eax, eax
0x180826b2d  jz      loc_180826C3E
0x180826b33  call    sub_1800A4464
0x180826b38  mov     ecx, eax
0x180826b3a  mov     rsi, 2C8DF3700h
0x180826b44  add     rcx, rsi
0x180826b47  imul    rcx, 989680h
0x180826b4e  mov     [rsp+110h+var_E0.dwLowDateTime], ecx
0x180826b52  shr     rcx, 20h
0x180826b56  mov     [rsp+110h+var_E0.dwHighDateTime], ecx
0x180826b5a  mov     rax, qword ptr [rsp+110h+var_E0.dwLowDateTime]
0x180826b5f  mov     qword ptr [rsp+110h+FileTime.dwLowDateTime], rax
0x180826b64  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180826b68  lea     rcx, [rsp+110h+FileTime]; lpFileTime
0x180826b6d  call    cs:FileTimeToSystemTime
0x180826b73  lea     rax, [rsi+rbx]
0x180826b77  imul    rax, 989680h
0x180826b7e  mov     [rsp+110h+var_E0.dwLowDateTime], eax
0x180826b82  shr     rax, 20h
0x180826b86  mov     [rsp+110h+var_E0.dwHighDateTime], eax
0x180826b8a  mov     rax, qword ptr [rsp+110h+var_E0.dwLowDateTime]
0x180826b8f  mov     qword ptr [rsp+110h+FileTime.dwLowDateTime], rax
0x180826b94  lea     rdx, [rbp+57h+var_80]; lpSystemTime
0x180826b98  lea     rcx, [rsp+110h+FileTime]; lpFileTime
0x180826b9d  call    cs:FileTimeToSystemTime
0x180826ba3  mov     qword ptr [rsp+110h+var_E0.dwLowDateTime], 0
0x180826bac  lea     rdx, [rsp+110h+var_E0]; lpFileTime
0x180826bb1  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180826bb5  call    cs:SystemTimeToFileTime
0x180826bbb  mov     rbx, qword ptr [rsp+110h+var_E0.dwLowDateTime]
0x180826bc0  mov     qword ptr [rsp+110h+FileTime.dwLowDateTime], 0
0x180826bc9  lea     rdx, [rsp+110h+FileTime]; lpFileTime
0x180826bce  lea     rcx, [rbp+57h+var_80]; lpSystemTime
0x180826bd2  call    cs:SystemTimeToFileTime
0x180826bd8  mov     rax, qword ptr [rsp+110h+FileTime.dwLowDateTime]
0x180826bdd  cmp     rbx, rax
0x180826be0  jbe     short loc_180826BE7
0x180826be2  sub     rbx, rax
0x180826be5  jmp     short loc_180826BED
0x180826be7  sub     rax, rbx
0x180826bea  mov     rbx, rax
0x180826bed  mov     rax, 0E5109EC205D7BEA7h
0x180826bf7  mul     rbx
0x180826bfa  shr     rdx, 1Dh
0x180826bfe  mov     qword ptr [rsp+110h+FileTime.dwLowDateTime], rdx
0x180826c03  shr     rdx, 20h
0x180826c07  mov     ebx, [rsp+110h+FileTime.dwLowDateTime]
0x180826c0b  or      eax, 0FFFFFFFFh
0x180826c0e  test    edx, edx
0x180826c10  cmovnz  ebx, eax
0x180826c13  call    sub_180827000
0x180826c18  mov     cl, [rax+2]
0x180826c1b  test    cl, cl
0x180826c1d  jz      short loc_180826C26
0x180826c1f  nop
0x180826c20  add     rax, 60h ; '`'
0x180826c24  jmp     short loc_180826C2F
0x180826c26  mov     rcx, rax
0x180826c29  call    cs:Mso20Win32Client_48723
0x180826c2f  imul    rcx, [rax], 3Ch ; '<'
0x180826c33  mov     eax, ebx
0x180826c35  cmp     rcx, rax
0x180826c38  jg      loc_180826FD0
0x180826c3e  mov     [rbp+57h+var_D0], 0
0x180826c46  xorps   xmm0, xmm0
0x180826c49  movdqu  [rbp+57h+var_B0], xmm0
0x180826c4e  mov     [rbp+57h+var_A0], 0
0x180826c56  mov     rbx, [rdi]
0x180826c59  mov     r14, [rdi+8]
0x180826c5d  mov     esi, 4
0x180826c62  lea     rdi, off_1810DD650
0x180826c69  cmp     rbx, r14
0x180826c6c  jz      loc_180826E47
0x180826c72  movdqa  xmm6, cs:xmmword_1810DD7D0
0x180826c7a  mov     rcx, rbx
0x180826c7d  call    sub_180111890
0x180826c82  test    al, al
0x180826c84  jnz     loc_180826E3A
0x180826c8a  mov     rdx, rbx
0x180826c8d  lea     rcx, [rsp+110h+FileTime]
0x180826c92  call    sub_180091D40
0x180826c97  mov     rdx, rax
0x180826c9a  lea     rcx, [rsp+110h+var_E0]
0x180826c9f  call    sub_18012B98C
0x180826ca4  nop
0x180826ca5  mov     rdx, rbx
0x180826ca8  lea     rcx, [rsp+110h+var_D8]
0x180826cad  call    sub_180091D40
0x180826cb2  mov     r9b, 1
0x180826cb5  xor     r8d, r8d
0x180826cb8  xor     edx, edx
0x180826cba  mov     rcx, rax
0x180826cbd  call    sub_1800B3B78
0x180826cc2  mov     rdx, qword ptr [rsp+110h+var_E0.dwLowDateTime]
0x180826cc7  test    rdx, rdx
0x180826cca  jz      loc_180826DBD
0x180826cd0  lea     rcx, [rbp+57h+var_C0]
0x180826cd4  call    sub_18082AE54
0x180826cd9  nop
0x180826cda  lea     rcx, [rbp+57h+var_C0]
0x180826cde  call    cs:?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180826ce4  test    al, al
0x180826ce6  jz      loc_180826DAC
0x180826cec  lea     rdx, [rbp+57h+var_C0]
0x180826cf0  lea     rcx, [rbp+57h+var_98]
0x180826cf4  call    ?GetTag@Jot@@YA?AV?$optional@VExceptionTag@Jot@@@std@@AEBVexception_ptr@3@@Z; Jot::GetTag(std::exception_ptr const &)
0x180826cf9  cmp     byte ptr [rax+4], 0
0x180826cfd  jz      short loc_180826D03
0x180826cff  mov     eax, [rax]
0x180826d01  jmp     short loc_180826D05
0x180826d03  xor     eax, eax
0x180826d05  cmp     eax, 10C57C7h
0x180826d0a  jz      loc_180826DAC
0x180826d10  inc     [rbp+57h+var_D0]
0x180826d14  xorps   xmm0, xmm0
0x180826d17  movdqu  xmmword ptr [rbp+57h+var_80.wYear], xmm0
0x180826d1c  lea     rdx, [rbp+57h+var_C0]
0x180826d20  lea     rcx, [rbp+57h+var_80]
0x180826d24  call    cs:?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180826d2a  lea     r8, [rbp+57h+var_80]
0x180826d2e  mov     rdx, rbx
0x180826d31  lea     rcx, [rbp+57h+var_70]
0x180826d35  call    sub_180AC6AF0
0x180826d3a  mov     rsi, rax
0x180826d3d  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x180826d41  cmp     rdi, [rbp+57h+var_A0]
0x180826d45  jz      short loc_180826D87
0x180826d47  mov     [rbp+57h+var_C8], rdi
0x180826d4b  mov     rdx, rax
0x180826d4e  mov     rcx, rdi
0x180826d51  call    sub_180091D40
0x180826d56  lea     rcx, [rdi+8]
0x180826d5a  mov     qword ptr [rcx], 0
0x180826d61  mov     qword ptr [rcx+8], 0
0x180826d69  lea     rdx, [rsi+8]
0x180826d6d  call    cs:?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180826d73  lea     rdx, [rsi+18h]
0x180826d77  lea     rcx, [rdi+18h]
0x180826d7b  call    sub_180269F54
0x180826d80  add     qword ptr [rbp+57h+var_B0+8], 38h ; '8'
0x180826d85  jmp     short loc_180826D97
0x180826d87  mov     r8, rsi
0x180826d8a  mov     rdx, rdi
0x180826d8d  lea     rcx, [rbp+57h+var_B0]
0x180826d91  call    sub_180AC65B4
0x180826d96  nop
0x180826d97  lea     rcx, [rbp+57h+var_70]
0x180826d9b  call    sub_180AC6E2C
0x180826da0  lea     rdi, off_1810DD650
0x180826da7  mov     esi, 4
0x180826dac  lea     rcx, [rbp+57h+var_C0]
0x180826db0  call    cs:?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180826db6  movdqu  [rbp+57h+var_C0], xmm6
0x180826dbb  jmp     short loc_180826E23
0x180826dbd  test    rax, rax
0x180826dc0  setnz   byte ptr [rsp+110h+var_E8]
0x180826dc5  lea     rax, off_18106B988
0x180826dcc  mov     [rbp+57h+var_70], rax
0x180826dd0  lea     rax, off_18109A188
0x180826dd7  mov     [rbp+57h+var_68], rax
0x180826ddb  lea     rax, aFhasidentity; "fHasIdentity"
0x180826de2  mov     [rbp+57h+var_60], rax
0x180826de6  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180826dee  lea     rax, [rsp+110h+var_E8]
0x180826df3  mov     [rbp+57h+var_50], rax
0x180826df7  mov     [rbp+57h+var_48], si
0x180826dfb  mov     qword ptr [rbp+57h+SystemTime.wYear], rdi
0x180826dff  lea     rax, aSigninpromptsf; "SignInPromptsForInvalidIdentitiesSkippe"...
0x180826e06  mov     qword ptr [rbp+57h+SystemTime.wHour], rax
0x180826e0a  lea     r9, [rbp+57h+var_70]
0x180826e0e  mov     r8d, 32h ; '2'
0x180826e14  lea     rdx, [rbp+57h+SystemTime]
0x180826e18  mov     ecx, 1E4943D9h
0x180826e1d  call    sub_180071198
0x180826e22  nop
0x180826e23  mov     rcx, qword ptr [rsp+110h+var_E0.dwLowDateTime]
0x180826e28  test    rcx, rcx
0x180826e2b  jz      short loc_180826E3A
0x180826e2d  mov     rax, [rcx]
0x180826e30  mov     rax, [rax+10h]
0x180826e34  call    cs:__guard_dispatch_icall_fptr
0x180826e3a  add     rbx, 8
0x180826e3e  cmp     rbx, r14
0x180826e41  jnz     loc_180826C7A
0x180826e47  mov     rax, [r15]
0x180826e4a  lea     rdx, [rsp+110h+FileTime]
0x180826e4f  mov     rcx, r15
0x180826e52  mov     rax, [rax+358h]
0x180826e59  call    cs:__guard_dispatch_icall_fptr
0x180826e5f  mov     rbx, [rax]
0x180826e62  mov     rcx, qword ptr [rsp+110h+FileTime.dwLowDateTime]
0x180826e67  test    rcx, rcx
0x180826e6a  jz      short loc_180826E82
0x180826e6c  mov     qword ptr [rsp+110h+FileTime.dwLowDateTime], 0
0x180826e75  mov     rax, [rcx]
0x180826e78  mov     rax, [rax+8]
0x180826e7c  call    cs:__guard_dispatch_icall_fptr
0x180826e82  test    rbx, rbx
0x180826e85  jz      short loc_180826EE8
0x180826e87  mov     r8b, 1
0x180826e8a  mov     rdx, rbx
0x180826e8d  lea     rcx, [rsp+110h+var_E0]
0x180826e92  call    sub_1808395A4
0x180826e97  lea     rax, [rsp+110h+var_D8]
0x180826e9c  mov     [rbp+57h+var_98], rax
0x180826ea0  lea     rdx, [rsp+110h+var_E0]
0x180826ea5  lea     rcx, [rsp+110h+var_D8]
0x180826eaa  call    sub_18004AD1C
0x180826eaf  mov     rbx, rax
0x180826eb2  mov     rdx, [r15]
0x180826eb5  mov     rcx, r15
0x180826eb8  mov     rax, [rdx+8]
0x180826ebc  call    cs:__guard_dispatch_icall_fptr
0x180826ec2  lea     r8, [rbp+57h+var_B0]
0x180826ec6  mov     rdx, rbx
0x180826ec9  mov     rcx, rax
0x180826ecc  call    sub_1805B1410
0x180826ed1  mov     rcx, qword ptr [rsp+110h+var_E0.dwLowDateTime]
0x180826ed6  test    rcx, rcx
0x180826ed9  jz      short loc_180826EE8
0x180826edb  mov     rax, [rcx]
0x180826ede  mov     rax, [rax+8]
0x180826ee2  call    cs:__guard_dispatch_icall_fptr
0x180826ee8  lea     rax, off_1810960B8
0x180826eef  mov     [rbp+57h+var_70], rax
0x180826ef3  lea     rax, off_1810D3080
0x180826efa  mov     [rbp+57h+var_68], rax
0x180826efe  lea     rax, aPromptednotebo; "promptedNotebooks"
0x180826f05  mov     [rbp+57h+var_60], rax
0x180826f09  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180826f11  lea     rax, [rbp+57h+var_D0]
0x180826f15  mov     [rbp+57h+var_50], rax
0x180826f19  mov     [rbp+57h+var_48], si
0x180826f1d  mov     edx, 2
0x180826f22  lea     rcx, [rbp+57h+var_98]
0x180826f26  call    sub_18002F61C
0x180826f2b  mov     qword ptr [rbp+57h+SystemTime.wYear], rdi
0x180826f2f  lea     rcx, aForcepromptfor; "ForcePromptForNotebookCheckRan"
0x180826f36  mov     qword ptr [rbp+57h+SystemTime.wHour], rcx
0x180826f3a  lea     r8, [rbp+57h+var_70]
0x180826f3e  mov     rdx, rax
0x180826f41  lea     rcx, [rbp+57h+SystemTime]
0x180826f45  call    sub_18002F2A0
0x180826f4a  call    ?UseRegistryCache@Jot@@YAPEAVCRegistryCache@1@XZ; Jot::UseRegistryCache(void)
0x180826f4f  lea     rdi, [rax+648h]
0x180826f56  mov     rax, [rdi]
0x180826f59  mov     rbx, [rax+8]
0x180826f5d  call    sub_1800A4464
0x180826f62  mov     edx, eax
0x180826f64  mov     rcx, rdi
0x180826f67  mov     rax, rbx
0x180826f6a  call    cs:__guard_dispatch_icall_fptr
0x180826f70  nop
0x180826f71  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180826f75  test    rcx, rcx
0x180826f78  jz      short loc_180826FD0
0x180826f7a  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x180826f7e  call    sub_180AC6580
0x180826f83  mov     rax, [rbp+57h+var_A0]
0x180826f87  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180826f8b  sub     rax, rcx
0x180826f8e  sar     rax, 3
0x180826f92  mov     rdx, 6DB6DB6DB6DB6DB7h
0x180826f9c  imul    rax, rdx
0x180826fa0  imul    rax, 38h ; '8'
0x180826fa4  mov     [rsp+110h+var_D8], rax
0x180826fa9  mov     qword ptr [rsp+110h+FileTime.dwLowDateTime], rcx
0x180826fae  cmp     rax, 1000h
0x180826fb4  jb      short loc_180826FCA
0x180826fb6  lea     rdx, [rsp+110h+var_D8]
0x180826fbb  lea     rcx, [rsp+110h+FileTime]
0x180826fc0  call    sub_18058B800
0x180826fc5  mov     rcx, qword ptr [rsp+110h+FileTime.dwLowDateTime]; Block
0x180826fca  call    cs:__imp_free
0x180826fd0  mov     rcx, [rbp+57h+var_38]
0x180826fd4  xor     rcx, rsp; StackCookie
0x180826fd7  call    __security_check_cookie
0x180826fdc  lea     r11, [rsp+110h+var_20]
0x180826fe4  mov     rbx, [r11+40h]
  ... truncated ...
```
