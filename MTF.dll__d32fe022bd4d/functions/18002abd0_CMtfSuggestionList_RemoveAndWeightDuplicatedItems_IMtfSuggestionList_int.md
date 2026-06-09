# CMtfSuggestionList::_RemoveAndWeightDuplicatedItems(IMtfSuggestionList *,int)

- ea: `0x18002abd0`
- end: `0x18002af75`
- name: `?_RemoveAndWeightDuplicatedItems@CMtfSuggestionList@@IEAAJPEAUIMtfSuggestionList@@H@Z`
- size: `933`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, struct IMtfSuggestionList *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800261d0`
- `0x180028860`

## callees

- `0x180002d88`
- `0x18002abd0`
- `0x18002bc56`
- `0x18002bc62`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ae67`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ae67`
- `OLEAUT32!__imp_SysStringLen` at `0x18002add2`
- `OLEAUT32!__imp_SysStringLen` at `0x18002adec`
- `OLEAUT32!__imp_SysStringLen` at `0x18002add2`
- `OLEAUT32!__imp_SysStringLen` at `0x18002adec`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::_RemoveAndWeightDuplicatedItems(
        CMtfSuggestionList *this,
        struct IMtfSuggestionList *a2,
        int a3)
{
  __int64 v3; // rax
  struct IMtfSuggestionList *v4; // r14
  int v6; // r12d
  __int64 (__fastcall *v7)(struct IMtfSuggestionList *, unsigned int *); // rax
  int v8; // ebx
  _QWORD *v9; // r15
  unsigned int v10; // esi
  __int64 v11; // rax
  unsigned int i; // esi
  __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // r14
  __int64 v17; // rdx
  unsigned int v18; // [rsp+28h] [rbp-59h] BYREF
  __int64 v19; // [rsp+30h] [rbp-51h] BYREF
  __int64 v20; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-41h] BYREF
  int v22; // [rsp+44h] [rbp-3Dh] BYREF
  __int64 v23; // [rsp+48h] [rbp-39h] BYREF
  _DWORD v24[4]; // [rsp+58h] [rbp-29h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-19h]
  unsigned int v28; // [rsp+100h] [rbp+7Fh] BYREF

  v3 = *(_QWORD *)a2;
  v4 = a2;
  v6 = a3;
  v18 = 0;
  v7 = *(__int64 (__fastcall **)(struct IMtfSuggestionList *, unsigned int *))(v3 + 24);
  v28 = 0;
  v8 = v7(a2, &v18);
  if ( v8 >= 0 )
    v8 = (*(__int64 (__fastcall **)(CMtfSuggestionList *, unsigned int *))(*(_QWORD *)this + 24LL))(this, &v28);
  if ( v18 && v28 )
  {
    v9 = operator new[](saturated_mul(v28, 8u));
    v10 = 0;
    if ( !v9 )
      v8 = -2147024882;
    if ( v28 )
    {
      do
      {
        if ( v8 < 0 )
          break;
        v19 = 0;
        v20 = 0;
        memset_0(v24, 0, 0x48u);
        v11 = *(_QWORD *)this;
        v24[0] = 2;
        pbstr = 0;
        v8 = (*(__int64 (__fastcall **)(CMtfSuggestionList *, _QWORD, __int64 *))(v11 + 32))(this, v10, &v19);
        if ( v8 >= 0 )
        {
          v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_IMtfSuggestionCandidate, &v20);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v20 + 40LL))(v20, v24);
            if ( v8 >= 0 )
              v9[v10] = pbstr;
          }
        }
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        ++v10;
      }
      while ( v10 < v28 );
    }
    for ( i = 0; i < v18; ++i )
    {
      if ( v8 < 0 )
        break;
      v19 = 0;
      v23 = 0;
      memset_0(v24, 0, 0x48u);
      v13 = *(_QWORD *)v4;
      v24[0] = 2;
      pbstr = 0;
      v8 = (*(__int64 (__fastcall **)(struct IMtfSuggestionList *, _QWORD, __int64 *))(v13 + 32))(v4, i, &v19);
      if ( v8 >= 0 )
      {
        v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_IMtfSuggestionCandidate, &v23);
        if ( v8 >= 0 )
          v8 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v23 + 40LL))(v23, v24);
      }
      v14 = (int)SysStringLen(pbstr);
      if ( v28 )
      {
        v15 = 0;
        if ( v8 < 0 )
        {
LABEL_29:
          v4 = a2;
        }
        else
        {
          while ( SysStringLen((BSTR)v9[v15]) != (_DWORD)v14 || memcmp_0((const void *)v9[v15], pbstr, 2 * v14) )
          {
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= v28 )
            {
              v6 = a3;
              goto LABEL_29;
            }
          }
          v6 = a3;
          if ( !a3 )
            goto LABEL_50;
          v21 = 0;
          v22 = 0;
          v20 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(v19, &v21);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(CMtfSuggestionList *, _QWORD, __int64 *))(*(_QWORD *)this + 32LL))(
                   this,
                   (unsigned int)v15,
                   &v20);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 24LL))(v20, &v22);
              v17 = v21 + v22;
              if ( (unsigned int)v17 < v21 )
                v17 = 0xFFFFFFFFLL;
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 32LL))(v20, v17);
            }
          }
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v8 < 0 )
          {
            v4 = a2;
          }
          else
          {
LABEL_50:
            v4 = a2;
            v8 = (*(__int64 (__fastcall **)(struct IMtfSuggestionList *, _QWORD))(*(_QWORD *)a2 + 56LL))(a2, i);
          }
          *((_BYTE *)this + 60) = 0;
          --i;
          --v18;
        }
      }
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v19 = 0;
      }
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    if ( v9 )
      operator delete[](v9);
    if ( v8 >= 0 && v6 )
      return (unsigned int)(*(__int64 (__fastcall **)(CMtfSuggestionList *, _QWORD))(*(_QWORD *)this + 80LL))(this, v28);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002abd0  mov     rax, rsp
0x18002abd3  mov     [rax+8], rbx
0x18002abd7  mov     [rax+18h], r8d
0x18002abdb  mov     [rax+10h], rdx
0x18002abdf  push    rbp
0x18002abe0  push    rsi
0x18002abe1  push    rdi
0x18002abe2  push    r12
0x18002abe4  push    r13
0x18002abe6  push    r14
0x18002abe8  push    r15
0x18002abea  lea     rbp, [rax-5Fh]
0x18002abee  sub     rsp, 0A0h
0x18002abf5  mov     rax, [rdx]
0x18002abf8  mov     r14, rdx
0x18002abfb  mov     rdi, rcx
0x18002abfe  lea     rdx, [rbp+57h+var_B0]
0x18002ac02  xor     r13d, r13d
0x18002ac05  mov     rcx, r14
0x18002ac08  mov     r12d, r8d
0x18002ac0b  mov     [rbp+57h+var_B0], r13d
0x18002ac0f  mov     rax, [rax+18h]
0x18002ac13  mov     [rbp+57h+arg_18], r13d
0x18002ac17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac1c  mov     ebx, eax
0x18002ac1e  test    eax, eax
0x18002ac20  js      short loc_18002AC37
0x18002ac22  mov     rax, [rdi]
0x18002ac25  lea     rdx, [rbp+57h+arg_18]
0x18002ac29  mov     rcx, rdi
0x18002ac2c  mov     rax, [rax+18h]
0x18002ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac35  mov     ebx, eax
0x18002ac37  cmp     [rbp+57h+var_B0], r13d
0x18002ac3b  jz      loc_18002AE8A
0x18002ac41  mov     eax, [rbp+57h+arg_18]
0x18002ac44  test    eax, eax
0x18002ac46  jz      loc_18002AE8A
0x18002ac4c  mov     ecx, eax
0x18002ac4e  mov     eax, 8
0x18002ac53  mul     rcx
0x18002ac56  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ac5d  cmovb   rax, rcx
0x18002ac61  mov     rcx, rax; unsigned __int64
0x18002ac64  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ac69  mov     r15, rax
0x18002ac6c  mov     esi, r13d
0x18002ac6f  test    r15, r15
0x18002ac72  mov     eax, 8007000Eh
0x18002ac77  cmovz   ebx, eax
0x18002ac7a  cmp     [rbp+57h+arg_18], r13d
0x18002ac7e  jbe     loc_18002AD46
0x18002ac84  test    ebx, ebx
0x18002ac86  js      loc_18002AD46
0x18002ac8c  xor     edx, edx; Val
0x18002ac8e  mov     [rbp+57h+var_A8], r13
0x18002ac92  lea     rcx, [rbp+57h+var_80]; void *
0x18002ac96  mov     [rbp+57h+var_A0], r13
0x18002ac9a  lea     r8d, [rdx+48h]; Size
0x18002ac9e  call    memset_0
0x18002aca3  mov     rax, [rdi]
0x18002aca6  lea     r8, [rbp+57h+var_A8]
0x18002acaa  mov     edx, esi
0x18002acac  mov     [rbp+57h+var_80], 2
0x18002acb3  mov     rcx, rdi
0x18002acb6  mov     [rbp+57h+pbstr], r13
0x18002acba  mov     rax, [rax+20h]
0x18002acbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acc3  mov     ebx, eax
0x18002acc5  test    eax, eax
0x18002acc7  js      short loc_18002AD0D
0x18002acc9  mov     rcx, [rbp+57h+var_A8]
0x18002accd  lea     r8, [rbp+57h+var_A0]
0x18002acd1  lea     rdx, IID_IMtfSuggestionCandidate
0x18002acd8  mov     rax, [rcx]
0x18002acdb  mov     rax, [rax]
0x18002acde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ace3  mov     ebx, eax
0x18002ace5  test    eax, eax
0x18002ace7  js      short loc_18002AD0D
0x18002ace9  mov     rcx, [rbp+57h+var_A0]
0x18002aced  lea     rdx, [rbp+57h+var_80]
0x18002acf1  mov     rax, [rcx]
0x18002acf4  mov     rax, [rax+28h]
0x18002acf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acfd  mov     ebx, eax
0x18002acff  test    eax, eax
0x18002ad01  js      short loc_18002AD0D
0x18002ad03  mov     rax, [rbp+57h+pbstr]
0x18002ad07  mov     ecx, esi
0x18002ad09  mov     [r15+rcx*8], rax
0x18002ad0d  mov     rcx, [rbp+57h+var_A8]
0x18002ad11  test    rcx, rcx
0x18002ad14  jz      short loc_18002AD26
0x18002ad16  mov     rax, [rcx]
0x18002ad19  mov     rax, [rax+10h]
0x18002ad1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad22  mov     [rbp+57h+var_A8], r13
0x18002ad26  mov     rcx, [rbp+57h+var_A0]
0x18002ad2a  test    rcx, rcx
0x18002ad2d  jz      short loc_18002AD3B
0x18002ad2f  mov     rax, [rcx]
0x18002ad32  mov     rax, [rax+10h]
0x18002ad36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad3b  inc     esi
0x18002ad3d  cmp     esi, [rbp+57h+arg_18]
0x18002ad40  jb      loc_18002AC84
0x18002ad46  mov     esi, r13d
0x18002ad49  cmp     [rbp+57h+var_B0], r13d
0x18002ad4d  jbe     loc_18002AE5F
0x18002ad53  test    ebx, ebx
0x18002ad55  js      loc_18002AE5F
0x18002ad5b  xor     edx, edx; Val
0x18002ad5d  mov     [rbp+57h+var_A8], r13
0x18002ad61  lea     rcx, [rbp+57h+var_80]; void *
0x18002ad65  mov     [rbp+57h+var_90], r13
0x18002ad69  lea     r8d, [rdx+48h]; Size
0x18002ad6d  call    memset_0
0x18002ad72  mov     rax, [r14]
0x18002ad75  lea     r8, [rbp+57h+var_A8]
0x18002ad79  mov     edx, esi
0x18002ad7b  mov     [rbp+57h+var_80], 2
0x18002ad82  mov     rcx, r14
0x18002ad85  mov     [rbp+57h+pbstr], r13
0x18002ad89  mov     rax, [rax+20h]
0x18002ad8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad92  mov     ebx, eax
0x18002ad94  test    eax, eax
0x18002ad96  js      short loc_18002ADCE
0x18002ad98  mov     rcx, [rbp+57h+var_A8]
0x18002ad9c  lea     r8, [rbp+57h+var_90]
0x18002ada0  lea     rdx, IID_IMtfSuggestionCandidate
0x18002ada7  mov     rax, [rcx]
0x18002adaa  mov     rax, [rax]
0x18002adad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb2  mov     ebx, eax
0x18002adb4  test    eax, eax
0x18002adb6  js      short loc_18002ADCE
0x18002adb8  mov     rcx, [rbp+57h+var_90]
0x18002adbc  lea     rdx, [rbp+57h+var_80]
0x18002adc0  mov     rax, [rcx]
0x18002adc3  mov     rax, [rax+28h]
0x18002adc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adcc  mov     ebx, eax
0x18002adce  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18002add2  call    cs:__imp_SysStringLen
0x18002add8  cmp     [rbp+57h+arg_18], 0
0x18002addc  movsxd  r13, eax
0x18002addf  jbe     short loc_18002AE23
0x18002ade1  xor     r14d, r14d
0x18002ade4  test    ebx, ebx
0x18002ade6  js      short loc_18002AE1F
0x18002ade8  mov     rcx, [r15+r14*8]; pbstr
0x18002adec  call    cs:__imp_SysStringLen
0x18002adf2  cmp     eax, r13d
0x18002adf5  jnz     short loc_18002AE12
0x18002adf7  mov     rdx, [rbp+57h+pbstr]; Buf2
0x18002adfb  mov     r8, r13
0x18002adfe  mov     rcx, [r15+r14*8]; Buf1
0x18002ae02  add     r8, r8; Size
0x18002ae05  call    memcmp_0
0x18002ae0a  test    eax, eax
0x18002ae0c  jz      loc_18002AEA7
0x18002ae12  inc     r14d
0x18002ae15  cmp     r14d, [rbp+57h+arg_18]
0x18002ae19  jb      short loc_18002ADE8
0x18002ae1b  mov     r12d, [rbp+57h+arg_10]
0x18002ae1f  mov     r14, [rbp+57h+arg_8]
0x18002ae23  xor     r13d, r13d
0x18002ae26  mov     rcx, [rbp+57h+var_A8]
0x18002ae2a  test    rcx, rcx
0x18002ae2d  jz      short loc_18002AE3F
0x18002ae2f  mov     rax, [rcx]
0x18002ae32  mov     rax, [rax+10h]
0x18002ae36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae3b  mov     [rbp+57h+var_A8], r13
0x18002ae3f  mov     rcx, [rbp+57h+var_90]
0x18002ae43  test    rcx, rcx
0x18002ae46  jz      short loc_18002AE54
0x18002ae48  mov     rax, [rcx]
0x18002ae4b  mov     rax, [rax+10h]
0x18002ae4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae54  inc     esi
0x18002ae56  cmp     esi, [rbp+57h+var_B0]
0x18002ae59  jb      loc_18002AD53
0x18002ae5f  test    r15, r15
0x18002ae62  jz      short loc_18002AE6D
0x18002ae64  mov     rcx, r15
0x18002ae67  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ae6d  test    ebx, ebx
0x18002ae6f  js      short loc_18002AE8A
0x18002ae71  test    r12d, r12d
0x18002ae74  jz      short loc_18002AE8A
0x18002ae76  mov     rax, [rdi]
0x18002ae79  mov     rcx, rdi
0x18002ae7c  mov     edx, [rbp+57h+arg_18]
0x18002ae7f  mov     rax, [rax+50h]
0x18002ae83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae88  mov     ebx, eax
0x18002ae8a  mov     eax, ebx
0x18002ae8c  mov     rbx, [rsp+0D0h+arg_0]
0x18002ae94  add     rsp, 0A0h
0x18002ae9b  pop     r15
0x18002ae9d  pop     r14
0x18002ae9f  pop     r13
0x18002aea1  pop     r12
0x18002aea3  pop     rdi
0x18002aea4  pop     rsi
0x18002aea5  pop     rbp
0x18002aea6  retn
0x18002aea7  mov     r12d, [rbp+57h+arg_10]
0x18002aeab  xor     r13d, r13d
0x18002aeae  test    r12d, r12d
0x18002aeb1  jz      loc_18002AF47
0x18002aeb7  mov     rcx, [rbp+57h+var_A8]
0x18002aebb  lea     rdx, [rbp+57h+var_98]
0x18002aebf  mov     [rbp+57h+var_98], r13d
0x18002aec3  mov     [rbp+57h+var_94], r13d
0x18002aec7  mov     [rbp+57h+var_A0], r13
0x18002aecb  mov     rax, [rcx]
0x18002aece  mov     rax, [rax+18h]
0x18002aed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed7  mov     ebx, eax
0x18002aed9  test    eax, eax
0x18002aedb  js      short loc_18002AF2E
0x18002aedd  mov     rax, [rdi]
0x18002aee0  lea     r8, [rbp+57h+var_A0]
0x18002aee4  mov     edx, r14d
0x18002aee7  mov     rcx, rdi
0x18002aeea  mov     rax, [rax+20h]
0x18002aeee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aef3  mov     ebx, eax
0x18002aef5  test    eax, eax
0x18002aef7  js      short loc_18002AF2E
0x18002aef9  mov     rcx, [rbp+57h+var_A0]
0x18002aefd  lea     rdx, [rbp+57h+var_94]
0x18002af01  mov     rax, [rcx]
0x18002af04  mov     rax, [rax+18h]
0x18002af08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af0d  mov     edx, [rbp+57h+var_94]
0x18002af10  mov     eax, 0FFFFFFFFh
0x18002af15  add     edx, [rbp+57h+var_98]
0x18002af18  mov     rcx, [rbp+57h+var_A0]
0x18002af1c  cmp     edx, [rbp+57h+var_98]
0x18002af1f  cmovb   edx, eax
0x18002af22  mov     rax, [rcx]
0x18002af25  mov     rax, [rax+20h]
0x18002af29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af2e  mov     rcx, [rbp+57h+var_A0]
0x18002af32  test    rcx, rcx
0x18002af35  jz      short loc_18002AF43
0x18002af37  mov     rax, [rcx]
0x18002af3a  mov     rax, [rax+10h]
0x18002af3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af43  test    ebx, ebx
0x18002af45  js      short loc_18002AF60
0x18002af47  mov     r14, [rbp+57h+arg_8]
0x18002af4b  mov     edx, esi
0x18002af4d  mov     rcx, r14
0x18002af50  mov     rax, [r14]
0x18002af53  mov     rax, [rax+38h]
0x18002af57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af5c  mov     ebx, eax
0x18002af5e  jmp     short loc_18002AF64
0x18002af60  mov     r14, [rbp+57h+arg_8]
0x18002af64  or      eax, 0FFFFFFFFh
0x18002af67  mov     [rdi+3Ch], r13b
0x18002af6b  add     esi, eax
0x18002af6d  add     [rbp+57h+var_B0], eax
0x18002af70  jmp     loc_18002AE26
```
