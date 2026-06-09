# AipGetPeImageVersionInfo

- ea: `0x14002ab78`
- end: `0x14002aef5`
- name: `AipGetPeImageVersionInfo`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14002a840`

## callees

- `0x140001610`
- `0x140001b3c`
- `0x140003730`
- `0x1400037cc`
- `0x140006a20`
- `0x140006c40`
- `0x14002ab78`
- `0x14002aefc`
- `0x14002f05c`
- `0x14002f21c`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14002ac5f`
- `ntoskrnl!KeStackAttachProcess` at `0x14002ac5f`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002ac55`
- `ntoskrnl!LdrResSearchResource` at `0x14002acad`
- `ntoskrnl!LdrResSearchResource` at `0x14002acad`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002aeaf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002aeaf`

## pseudocode

```c
__int64 __fastcall AipGetPeImageVersionInfo(
        void *a1,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        _OWORD *a6,
        _OWORD *a7)
{
  int v10; // r12d
  int v11; // ebx
  unsigned __int16 *v12; // rcx
  size_t v13; // rdx
  __int64 v14; // r15
  unsigned int v15; // r14d
  size_t v16; // rsi
  void *v17; // rax
  __int64 v18; // rcx
  unsigned __int16 v19; // si
  __int64 v21; // [rsp+20h] [rbp-208h]
  size_t pcbLength; // [rsp+48h] [rbp-1E0h] BYREF
  int v23; // [rsp+50h] [rbp-1D8h]
  unsigned int v24; // [rsp+54h] [rbp-1D4h]
  unsigned __int64 v25; // [rsp+58h] [rbp-1D0h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-1C8h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+68h] [rbp-1C0h] BYREF
  unsigned __int16 *v28; // [rsp+70h] [rbp-1B8h] BYREF
  _QWORD v29[2]; // [rsp+78h] [rbp-1B0h]
  _OWORD v30[2]; // [rsp+88h] [rbp-1A0h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-180h]
  struct _KAPC_STATE ApcState; // [rsp+B0h] [rbp-178h] BYREF
  WCHAR pszDest[128]; // [rsp+E0h] [rbp-148h] BYREF

  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v26 = 0;
  v28 = 0;
  v25 = 0;
  pcbLength = 0;
  psz = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = 0;
  v23 = 0;
  v29[0] = a7;
  v29[1] = a6;
  *a7 = 0;
  *a6 = 0;
  v11 = SrppMapFileImage(a1, (__int64)v30);
  if ( v11 >= 0 )
  {
    if ( !(_BYTE)v31 )
    {
      KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
      v10 = 1;
      v23 = 1;
    }
    if ( (int)LdrResSearchResource(*((_QWORD *)&v30[0] + 1), qword_14000D578, 3, 4624, &v26, &v25, 0, 0) < 0 )
      goto LABEL_26;
    if ( v25 < 0x5C )
      goto LABEL_26;
    v12 = v26;
    if ( *v26 > v25 || *((_DWORD *)v26 + 10) != -17890115 )
      goto LABEL_26;
    *a2 = *((_DWORD *)v26 + 12);
    *a3 = *((_DWORD *)v12 + 13);
    *a4 = *((_DWORD *)v12 + 14);
    *a5 = *((_DWORD *)v12 + 15);
    v11 = AipQueryValue(v12, L"\\VarFileInfo\\Translation", &v28, &pcbLength);
    if ( v11 < 0 )
      goto LABEL_27;
    if ( pcbLength < 4 || ((unsigned __int8)v28 & 1) != 0 )
    {
LABEL_26:
      v11 = -2;
    }
    else
    {
      LODWORD(v21) = v28[1];
      RtlStringCbPrintfW(pszDest, 0x100u, L"\\StringFileInfo\\%04x%04x\\", *v28, v21);
      v14 = -1;
      do
        ++v14;
      while ( pszDest[v14] );
      v15 = 0;
      v24 = 0;
      while ( v15 < 2 )
      {
        if ( 2 * (unsigned __int64)(unsigned int)v14 >= 0x100 )
          _report_rangecheckfailure();
        pszDest[(unsigned int)v14] = 0;
        RtlStringCbCatW(pszDest, v13, off_1400096C8[v15]);
        if ( (int)AipQueryValue(v26, pszDest, &psz, &pcbLength) < 0 || (v13 = pcbLength, pcbLength - 1 > 0xFFFE) )
        {
          v11 = 0;
        }
        else
        {
          v11 = RtlStringCbLengthW(psz, 2 * pcbLength, &pcbLength);
          if ( v11 >= 0 && pcbLength )
          {
            v16 = pcbLength + 2;
            pcbLength = v16;
            v17 = (void *)AiAlloc(v16);
            v18 = v29[v15];
            *(_QWORD *)(v18 + 8) = v17;
            if ( !v17 )
            {
              v11 = -1073741801;
              break;
            }
            v19 = v16 - 2;
            *(_WORD *)v18 = v19;
            *(_WORD *)(v18 + 2) = v19;
            memmove(v17, psz, v19);
          }
          else
          {
            v11 = 0;
          }
        }
        v24 = ++v15;
      }
    }
  }
LABEL_27:
  if ( v10 )
    KeUnstackDetachProcess(&ApcState);
  SrppUnmapFileImage(v30);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002ab78  push    rbx
0x14002ab7a  push    rsi
0x14002ab7b  push    rdi
0x14002ab7c  push    r12
0x14002ab7e  push    r13
0x14002ab80  push    r14
0x14002ab82  push    r15
0x14002ab84  sub     rsp, 1F0h
0x14002ab8b  mov     rax, cs:__security_cookie
0x14002ab92  xor     rax, rsp
0x14002ab95  mov     [rsp+228h+var_48], rax
0x14002ab9d  mov     r15, r9
0x14002aba0  mov     r14, r8
0x14002aba3  mov     rsi, rdx
0x14002aba6  mov     r13, [rsp+228h+arg_20]
0x14002abae  mov     r10, [rsp+228h+arg_28]
0x14002abb6  mov     rax, [rsp+228h+arg_30]
0x14002abbe  xorps   xmm0, xmm0
0x14002abc1  xor     edx, edx
0x14002abc3  movups  [rsp+228h+var_1A0], xmm0
0x14002abcb  movups  [rsp+228h+var_190], xmm0
0x14002abd3  mov     [rsp+228h+var_180], rdx
0x14002abdb  xor     edi, edi
0x14002abdd  mov     [rsp+228h+var_1C8], rdi
0x14002abe2  mov     [rsp+228h+var_1B8], rdi
0x14002abe7  mov     [rsp+228h+var_1D0], rdi
0x14002abec  mov     [rsp+228h+pcbLength], rdi
0x14002abf1  mov     [rsp+228h+psz], rdi
0x14002abf6  movups  xmmword ptr [rsp+228h+ApcState.ApcListHead.Flink], xmm0
0x14002abfe  movups  xmmword ptr [rsp+228h+ApcState.ApcListHead.Flink+10h], xmm0
0x14002ac06  movups  xmmword ptr [rsp+228h+ApcState.Process], xmm0
0x14002ac0e  mov     r12d, edi
0x14002ac11  mov     [rsp+228h+var_1D8], edi
0x14002ac15  mov     [rsp+228h+var_1B0], rax
0x14002ac1a  mov     [rsp+228h+var_1A8], r10
0x14002ac22  movups  xmmword ptr [rax], xmm0
0x14002ac25  xorps   xmm1, xmm1
0x14002ac28  movups  xmmword ptr [r10], xmm1
0x14002ac2c  lea     rdx, [rsp+228h+var_1A0]
0x14002ac34  call    SrppMapFileImage
0x14002ac39  mov     ebx, eax
0x14002ac3b  test    eax, eax
0x14002ac3d  js      loc_14002AEA2
0x14002ac43  cmp     byte ptr [rsp+228h+var_180], dil
0x14002ac4b  jnz     short loc_14002AC74
0x14002ac4d  lea     rdx, [rsp+228h+ApcState]; ApcState
0x14002ac55  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002ac5c  mov     rcx, [rcx]; PROCESS
0x14002ac5f  call    cs:__imp_KeStackAttachProcess
0x14002ac66  nop     dword ptr [rax+rax+00h]
0x14002ac6b  lea     r12d, [rdi+1]
0x14002ac6f  mov     [rsp+228h+var_1D8], r12d
0x14002ac74  mov     [rsp+228h+var_1F0], rdi
0x14002ac79  mov     [rsp+228h+var_1F8], rdi
0x14002ac7e  lea     rax, [rsp+228h+var_1D0]
0x14002ac83  mov     [rsp+228h+var_200], rax
0x14002ac88  lea     rax, [rsp+228h+var_1C8]
0x14002ac8d  mov     [rsp+228h+var_208], rax
0x14002ac92  mov     r9d, 1210h
0x14002ac98  mov     r8d, 3
0x14002ac9e  lea     rdx, qword_14000D578
0x14002aca5  mov     rcx, qword ptr [rsp+228h+var_1A0+8]
0x14002acad  call    cs:__imp_LdrResSearchResource
0x14002acb4  nop     dword ptr [rax+rax+00h]
0x14002acb9  mov     [rsp+228h+var_1E8], eax
0x14002acbd  test    eax, eax
0x14002acbf  js      loc_14002AE8C
0x14002acc5  cmp     [rsp+228h+var_1D0], 5Ch ; '\'
0x14002accb  jb      loc_14002AE8C
0x14002acd1  mov     rcx, [rsp+228h+var_1C8]
0x14002acd6  movzx   eax, word ptr [rcx]
0x14002acd9  cmp     rax, [rsp+228h+var_1D0]
0x14002acde  ja      loc_14002AE8C
0x14002ace4  cmp     dword ptr [rcx+28h], 0FEEF04BDh
0x14002aceb  jnz     loc_14002AE8C
0x14002acf1  mov     eax, [rcx+30h]
0x14002acf4  mov     [rsi], eax
0x14002acf6  mov     eax, [rcx+34h]
0x14002acf9  mov     [r14], eax
0x14002acfc  mov     eax, [rcx+38h]
0x14002acff  mov     [r15], eax
0x14002ad02  mov     eax, [rcx+3Ch]
0x14002ad05  mov     [r13+0], eax
0x14002ad09  lea     r9, [rsp+228h+pcbLength]
0x14002ad0e  lea     r8, [rsp+228h+var_1B8]
0x14002ad13  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x14002ad1a  call    AipQueryValue
0x14002ad1f  mov     ebx, eax
0x14002ad21  mov     [rsp+228h+var_1E8], eax
0x14002ad25  test    eax, eax
0x14002ad27  js      loc_14002AE95
0x14002ad2d  cmp     [rsp+228h+pcbLength], 4
0x14002ad33  jb      loc_14002AE8C
0x14002ad39  mov     rcx, [rsp+228h+var_1B8]
0x14002ad3e  test    cl, 1
0x14002ad41  jnz     loc_14002AE8C
0x14002ad47  movzx   eax, word ptr [rcx+2]
0x14002ad4b  movzx   r9d, word ptr [rcx]
0x14002ad4f  mov     dword ptr [rsp+228h+var_208], eax
0x14002ad53  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\"
0x14002ad5a  mov     edx, 100h; cbDest
0x14002ad5f  lea     rcx, [rsp+228h+pszDest]; pszDest
0x14002ad67  call    RtlStringCbPrintfW
0x14002ad6c  lea     rax, [rsp+228h+pszDest]
0x14002ad74  or      r15, 0FFFFFFFFFFFFFFFFh
0x14002ad78  inc     r15
0x14002ad7b  cmp     [rax+r15*2], di
0x14002ad80  jnz     short loc_14002AD78
0x14002ad82  mov     r14d, edi
0x14002ad85  mov     [rsp+228h+var_1D4], edi
0x14002ad89  mov     eax, 2
0x14002ad8e  cmp     r14d, eax
0x14002ad91  jnb     loc_14002AE95
0x14002ad97  mov     eax, r15d
0x14002ad9a  add     rax, rax
0x14002ad9d  cmp     rax, 100h
0x14002ada3  jnb     loc_14002AEEE
0x14002ada9  mov     [rsp+rax+228h+pszDest], di
0x14002adb1  mov     r13d, r14d
0x14002adb4  lea     r8, off_1400096C8; "OriginalFileName"
0x14002adbb  mov     r8, [r8+r13*8]; pszSrc
0x14002adbf  lea     rcx, [rsp+228h+pszDest]; pszDest
0x14002adc7  call    RtlStringCbCatW
0x14002adcc  lea     r9, [rsp+228h+pcbLength]
0x14002add1  lea     r8, [rsp+228h+psz]
0x14002add6  lea     rdx, [rsp+228h+pszDest]
0x14002adde  mov     rcx, [rsp+228h+var_1C8]
0x14002ade3  call    AipQueryValue
0x14002ade8  mov     [rsp+228h+var_1E8], eax
0x14002adec  test    eax, eax
0x14002adee  js      loc_14002AE79
0x14002adf4  mov     rdx, [rsp+228h+pcbLength]
0x14002adf9  lea     rax, [rdx-1]
0x14002adfd  cmp     rax, 0FFFEh
0x14002ae03  ja      short loc_14002AE79
0x14002ae05  add     rdx, rdx; cbMax
0x14002ae08  lea     r8, [rsp+228h+pcbLength]; pcbLength
0x14002ae0d  mov     rcx, [rsp+228h+psz]; psz
0x14002ae12  call    RtlStringCbLengthW
0x14002ae17  mov     ebx, eax
0x14002ae19  mov     [rsp+228h+var_1E8], eax
0x14002ae1d  test    eax, eax
0x14002ae1f  js      short loc_14002AE71
0x14002ae21  mov     rsi, [rsp+228h+pcbLength]
0x14002ae26  test    rsi, rsi
0x14002ae29  jz      short loc_14002AE71
0x14002ae2b  add     rsi, 2
0x14002ae2f  mov     [rsp+228h+pcbLength], rsi
0x14002ae34  mov     rcx, rsi
0x14002ae37  call    AiAlloc
0x14002ae3c  mov     rcx, [rsp+r13*8+228h+var_1B0]
0x14002ae41  mov     [rcx+8], rax
0x14002ae45  test    rax, rax
0x14002ae48  jnz     short loc_14002AE51
0x14002ae4a  mov     ebx, 0C0000017h
0x14002ae4f  jmp     short loc_14002AE91
0x14002ae51  sub     si, 2
0x14002ae55  movzx   r8d, si; Size
0x14002ae59  mov     [rcx], r8w
0x14002ae5d  mov     [rcx+2], r8w
0x14002ae62  mov     rdx, [rsp+228h+psz]; Src
0x14002ae67  mov     rcx, rax; void *
0x14002ae6a  call    memmove
0x14002ae6f  jmp     short loc_14002AE77
0x14002ae71  mov     ebx, edi
0x14002ae73  mov     [rsp+228h+var_1E8], ebx
0x14002ae77  jmp     short loc_14002AE7F
0x14002ae79  mov     ebx, edi
0x14002ae7b  mov     [rsp+228h+var_1E8], ebx
0x14002ae7f  inc     r14d
0x14002ae82  mov     [rsp+228h+var_1D4], r14d
0x14002ae87  jmp     loc_14002AD89
0x14002ae8c  mov     ebx, 0FFFFFFFEh
0x14002ae91  mov     [rsp+228h+var_1E8], ebx
0x14002ae95  jmp     short loc_14002AEA2
0x14002ae97  mov     ebx, eax
0x14002ae99  mov     [rsp+228h+var_1E8], eax
0x14002ae9d  mov     r12d, [rsp+228h+var_1D8]
0x14002aea2  test    r12d, r12d
0x14002aea5  jz      short loc_14002AEBB
0x14002aea7  lea     rcx, [rsp+228h+ApcState]; ApcState
0x14002aeaf  call    cs:__imp_KeUnstackDetachProcess
0x14002aeb6  nop     dword ptr [rax+rax+00h]
0x14002aebb  lea     rcx, [rsp+228h+var_1A0]
0x14002aec3  call    SrppUnmapFileImage
0x14002aec8  mov     eax, ebx
0x14002aeca  mov     rcx, [rsp+228h+var_48]
0x14002aed2  xor     rcx, rsp; StackCookie
0x14002aed5  call    __security_check_cookie
0x14002aeda  add     rsp, 1F0h
0x14002aee1  pop     r15
0x14002aee3  pop     r14
0x14002aee5  pop     r13
0x14002aee7  pop     r12
0x14002aee9  pop     rdi
0x14002aeea  pop     rsi
0x14002aeeb  pop     rbx
0x14002aeec  retn
0x14002aeee  call    __report_rangecheckfailure
```
