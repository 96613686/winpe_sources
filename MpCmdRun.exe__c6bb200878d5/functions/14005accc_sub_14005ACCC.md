# sub_14005ACCC

- ea: `0x14005accc`
- end: `0x14005b12b`
- name: `sub_14005ACCC`
- size: `1119`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14005abac`
- `0x14005cdec`
- `0x14005d280`
- `0x14005dcb0`

## callees

- `0x140045e84`
- `0x14004ed80`
- `0x14004edcc`
- `0x14004edf0`
- `0x14005a680`
- `0x14005a87c`
- `0x14005accc`
- `0x14005cae4`
- `0x1400659c0`
- `0x140065a20`
- `0x14006b28c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005af6e`
- `KERNEL32!GetLastError` at `0x14005b0bf`
- `KERNEL32!GetLastError` at `0x14005af6e`
- `KERNEL32!GetLastError` at `0x14005b0bf`
- `KERNEL32!ReadFile` at `0x14005afbd`
- `KERNEL32!ReadFile` at `0x14005afbd`
- `KERNEL32!GetConsoleMode` at `0x14005af2f`
- `KERNEL32!GetConsoleMode` at `0x14005af2f`
- `KERNEL32!ReadConsoleW` at `0x14005af64`
- `KERNEL32!ReadConsoleW` at `0x14005af64`

## pseudocode

```c
__int64 __fastcall sub_14005ACCC(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned int v3; // r13d
  __int16 *v4; // r9
  unsigned __int64 v5; // r12
  __int64 v6; // rdx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // ecx
  __int16 *v11; // rbx
  int v12; // r10d
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // ecx
  DWORD v16; // ebp
  __int16 *v17; // r15
  __int64 v18; // rdx
  int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // edi
  char v27; // al
  char v28; // cl
  char v29; // cl
  DWORD LastError; // eax
  int v31; // edi
  unsigned __int64 v33; // rdx
  int v34; // eax
  unsigned __int64 v35; // r8
  __int16 *v36; // r10
  __int16 *v37; // rax
  __int16 *v38; // rdi
  unsigned __int64 v39; // r9
  __int16 v40; // cx
  __int64 v41; // r11
  __int64 v42; // rdx
  int v43; // ecx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rdx
  int v49; // ecx
  DWORD Mode; // [rsp+30h] [rbp-68h] BYREF
  HANDLE hConsoleHandle; // [rsp+38h] [rbp-60h]
  unsigned __int64 v52; // [rsp+40h] [rbp-58h]
  __int64 v53; // [rsp+48h] [rbp-50h]
  __int16 *v54; // [rsp+50h] [rbp-48h]
  char v55; // [rsp+A0h] [rbp+8h]
  int v56; // [rsp+A8h] [rbp+10h]
  DWORD NumberOfCharsRead; // [rsp+B8h] [rbp+20h] BYREF

  v56 = a2;
  v3 = a1;
  v4 = (__int16 *)a2;
  v5 = (unsigned int)a3;
  if ( (_DWORD)a1 != -2 )
  {
    if ( (int)a1 >= 0
      && (unsigned int)a1 < dword_140195670
      && (a2 = 1,
          v53 = 1,
          a3 = (unsigned __int64)(int)a1 >> 6,
          v52 = a3,
          v8 = qword_140195270[a3],
          (*(_BYTE *)(v8 + 72 * (a1 & 0x3F) + 56) & 1) != 0) )
    {
      if ( (unsigned int)v5 <= 0x7FFFFFFF )
      {
        if ( !(_DWORD)v5 || (*(_BYTE *)(v8 + 72 * (a1 & 0x3F) + 56) & 2) != 0 )
          return 0;
        if ( v4 )
        {
          v11 = 0;
          v12 = *(char *)(v8 + 72 * (a1 & 0x3F) + 57);
          hConsoleHandle = *(HANDLE *)(v8 + 72 * (a1 & 0x3F) + 40);
          v55 = v12;
          v13 = (unsigned int)(v12 - 1);
          if ( v12 == 1 )
          {
            if ( (v5 & 1) != 0 )
            {
LABEL_14:
              *(_DWORD *)sub_14004EDCC(v13, 1, a3, v4) = 0;
              *(_DWORD *)sub_14004EDF0(v15, v14) = 22;
              invalid_parameter_noinfo();
LABEL_38:
              v31 = -1;
              goto LABEL_39;
            }
            v16 = (unsigned int)v5 >> 1;
            if ( (unsigned int)v5 >> 1 < 4 )
              v16 = 4;
            v11 = (__int16 *)malloc_base(v16);
            free_base(0);
            free_base(0);
            v17 = v11;
            if ( !v11 )
            {
              *(_DWORD *)sub_14004EDF0(v19, v18) = 12;
              *(_DWORD *)sub_14004EDCC(v21, v20, v22, v23) = 8;
              goto LABEL_38;
            }
            v24 = lseeki64_nolock(v3, 0, 1);
            a3 = v52;
            LOBYTE(v12) = v55;
            *(_QWORD *)(qword_140195270[v52] + 72LL * (v3 & 0x3F) + 48) = v24;
          }
          else
          {
            if ( v12 == 2 && (v5 & 1) != 0 )
              goto LABEL_14;
            v16 = v5;
            v17 = v4;
          }
          v25 = qword_140195270[a3];
          v26 = 0;
          v54 = v17;
          if ( (*(_BYTE *)(v25 + 72LL * (v3 & 0x3F) + 56) & 0x48) != 0 )
          {
            v27 = *(_BYTE *)(v25 + 72LL * (v3 & 0x3F) + 58);
            if ( v27 != 10 )
            {
              *(_BYTE *)v17 = v27;
              --v16;
              v17 = (__int16 *)((char *)v17 + 1);
              v26 = 1;
              *(_BYTE *)(qword_140195270[a3] + 72LL * (v3 & 0x3F) + 58) = 10;
              if ( (_BYTE)v12 )
              {
                v28 = *(_BYTE *)(qword_140195270[a3] + 72LL * (v3 & 0x3F) + 59);
                if ( v28 != 10 )
                {
                  if ( v16 )
                  {
                    *(_BYTE *)v17 = v28;
                    v26 = 2;
                    v17 = (__int16 *)((char *)v17 + 1);
                    --v16;
                    *(_BYTE *)(qword_140195270[a3] + 72LL * (v3 & 0x3F) + 59) = 10;
                    if ( (_BYTE)v12 == 1 )
                    {
                      v29 = *(_BYTE *)(qword_140195270[a3] + 72LL * (v3 & 0x3F) + 60);
                      if ( v29 != 10 )
                      {
                        if ( v16 )
                        {
                          *(_BYTE *)v17 = v29;
                          v26 = 3;
                          v17 = (__int16 *)((char *)v17 + 1);
                          --v16;
                          *(_BYTE *)(qword_140195270[a3] + 72LL * (v3 & 0x3F) + 60) = 10;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          Mode = 0;
          if ( isatty(v3)
            && *(char *)(qword_140195270[v52] + 72LL * (v3 & 0x3F) + 56) < 0
            && GetConsoleMode(hConsoleHandle, &Mode) )
          {
            if ( v55 == 2 )
            {
              NumberOfCharsRead = 0;
              if ( !ReadConsoleW(hConsoleHandle, v17, v16 >> 1, &NumberOfCharsRead, 0) )
              {
                LastError = GetLastError();
LABEL_37:
                sub_14004ED80(LastError);
                goto LABEL_38;
              }
              v31 = v26 + 2 * NumberOfCharsRead;
              goto LABEL_45;
            }
          }
          else
          {
            LOBYTE(v53) = 0;
          }
          NumberOfCharsRead = 0;
          if ( !ReadFile(hConsoleHandle, v17, v16, &NumberOfCharsRead, 0) || NumberOfCharsRead > (unsigned int)v5 )
          {
            LastError = GetLastError();
            if ( LastError == 5 )
            {
              *(_DWORD *)sub_14004EDF0(v43, v42) = 9;
              *(_DWORD *)sub_14004EDCC(v45, v44, v46, v47) = 5;
              goto LABEL_38;
            }
            if ( LastError == 109 )
            {
              v31 = 0;
              goto LABEL_39;
            }
            goto LABEL_37;
          }
          v31 = NumberOfCharsRead + v26;
LABEL_45:
          v33 = v52;
          if ( *(char *)(qword_140195270[v52] + 72LL * (v3 & 0x3F) + 56) < 0 )
          {
            if ( v55 == 2 )
            {
              v35 = (unsigned __int64)v31 >> 1;
              if ( (_BYTE)v53 )
              {
                v36 = v54;
                v37 = v54;
                v38 = v54;
                v39 = (unsigned __int64)&v54[v35];
                if ( (unsigned __int64)v54 < v39 )
                {
                  while ( 1 )
                  {
                    v40 = *v37;
                    if ( *v37 == 26 )
                      break;
                    if ( v40 == 13 && (unsigned __int64)(v37 + 1) < v39 && v37[1] == 10 )
                    {
                      v40 = 10;
                      v41 = 4;
                    }
                    else
                    {
                      v41 = 2;
                    }
                    v37 = (__int16 *)((char *)v37 + v41);
                    *v38++ = v40;
                    if ( (unsigned __int64)v37 >= v39 )
                      goto LABEL_60;
                  }
                  *(_BYTE *)(qword_140195270[v33] + 72LL * (v3 & 0x3F) + 56) |= 2u;
                }
LABEL_60:
                v31 = 2 * (v38 - v36);
                goto LABEL_39;
              }
              v34 = sub_14005A680(v3, v54, v35);
            }
            else
            {
              v34 = sub_14005A87C(v3, (_DWORD)v17, v31, v56, v5 >> 1);
            }
            v31 = v34;
          }
LABEL_39:
          free_base(v11);
          return (unsigned int)v31;
        }
      }
      *(_DWORD *)sub_14004EDCC(a1, 1, a3, v4) = 0;
      *(_DWORD *)sub_14004EDF0(v10, v9) = 22;
    }
    else
    {
      *(_DWORD *)sub_14004EDCC(a1, a2, a3, v4) = 0;
      *(_DWORD *)sub_14004EDF0(v49, v48) = 9;
    }
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  *(_DWORD *)sub_14004EDCC(a1, a2, a3, a2) = 0;
  *(_DWORD *)sub_14004EDF0(v7, v6) = 9;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14005accc  mov     [rsp+arg_10], rbx
0x14005acd1  mov     [rsp+arg_8], rdx
0x14005acd6  push    rbp
0x14005acd7  push    rsi
0x14005acd8  push    rdi
0x14005acd9  push    r12
0x14005acdb  push    r13
0x14005acdd  push    r14
0x14005acdf  push    r15
0x14005ace1  sub     rsp, 60h
0x14005ace5  movsxd  r13, ecx
0x14005ace8  mov     r9, rdx
0x14005aceb  mov     r12d, r8d
0x14005acee  cmp     r13d, 0FFFFFFFEh
0x14005acf2  jnz     short loc_14005AD0D
0x14005acf4  call    sub_14004EDCC
0x14005acf9  xor     esi, esi
0x14005acfb  mov     [rax], esi
0x14005acfd  call    sub_14004EDF0
0x14005ad02  mov     dword ptr [rax], 9
0x14005ad08  jmp     loc_14005B110
0x14005ad0d  xor     esi, esi
0x14005ad0f  test    ecx, ecx
0x14005ad11  js      loc_14005B0F9
0x14005ad17  cmp     r13d, cs:dword_140195670
0x14005ad1e  jnb     loc_14005B0F9
0x14005ad24  mov     rax, r13
0x14005ad27  lea     edx, [rsi+1]
0x14005ad2a  and     eax, 3Fh
0x14005ad2d  mov     [rsp+98h+var_50], rdx
0x14005ad32  mov     r8, r13
0x14005ad35  lea     r11, qword_140195270
0x14005ad3c  shr     r8, 6
0x14005ad40  mov     [rsp+98h+var_58], r8
0x14005ad45  lea     r14, [rax+rax*8]
0x14005ad49  mov     rax, [r11+r8*8]
0x14005ad4d  test    [rax+r14*8+38h], dl
0x14005ad52  jz      loc_14005B0F9
0x14005ad58  cmp     r12d, 7FFFFFFFh
0x14005ad5f  jbe     short loc_14005AD78
0x14005ad61  call    sub_14004EDCC
0x14005ad66  mov     [rax], esi
0x14005ad68  call    sub_14004EDF0
0x14005ad6d  mov     dword ptr [rax], 16h
0x14005ad73  jmp     loc_14005B10B
0x14005ad78  test    r12d, r12d
0x14005ad7b  jz      loc_14005B0F5
0x14005ad81  test    byte ptr [rax+r14*8+38h], 2
0x14005ad87  jnz     loc_14005B0F5
0x14005ad8d  test    r9, r9
0x14005ad90  jz      short loc_14005AD61
0x14005ad92  mov     rcx, [rax+r14*8+28h]
0x14005ad97  mov     rbx, rsi
0x14005ad9a  movsx   r10d, byte ptr [rax+r14*8+39h]
0x14005ada0  mov     edi, 4
0x14005ada5  mov     [rsp+98h+hConsoleHandle], rcx
0x14005adaa  mov     ecx, r10d
0x14005adad  mov     [rsp+98h+arg_0], r10b
0x14005adb5  sub     ecx, edx
0x14005adb7  jz      short loc_14005ADEA
0x14005adb9  cmp     ecx, edx
0x14005adbb  jnz     short loc_14005ADE2
0x14005adbd  mov     eax, r12d
0x14005adc0  not     eax
0x14005adc2  test    dl, al
0x14005adc4  jnz     short loc_14005ADE2
0x14005adc6  call    sub_14004EDCC
0x14005adcb  mov     [rax], esi
0x14005adcd  call    sub_14004EDF0
0x14005add2  mov     dword ptr [rax], 16h
0x14005add8  call    _invalid_parameter_noinfo
0x14005addd  jmp     loc_14005AF7B
0x14005ade2  mov     ebp, r12d
0x14005ade5  mov     r15, r9
0x14005ade8  jmp     short loc_14005AE68
0x14005adea  mov     eax, r12d
0x14005aded  not     eax
0x14005adef  test    dl, al
0x14005adf1  jz      short loc_14005ADC6
0x14005adf3  mov     ebp, r12d
0x14005adf6  shr     ebp, 1
0x14005adf8  cmp     ebp, edi
0x14005adfa  cmovb   ebp, edi
0x14005adfd  mov     ecx, ebp; Size
0x14005adff  call    _malloc_base
0x14005ae04  xor     ecx, ecx; Block
0x14005ae06  mov     rbx, rax
0x14005ae09  call    _free_base
0x14005ae0e  xor     ecx, ecx; Block
0x14005ae10  call    _free_base
0x14005ae15  mov     r15, rbx
0x14005ae18  test    rbx, rbx
0x14005ae1b  jnz     short loc_14005AE38
0x14005ae1d  call    sub_14004EDF0
0x14005ae22  mov     dword ptr [rax], 0Ch
0x14005ae28  call    sub_14004EDCC
0x14005ae2d  mov     dword ptr [rax], 8
0x14005ae33  jmp     loc_14005AF7B
0x14005ae38  xor     edx, edx
0x14005ae3a  mov     ecx, r13d
0x14005ae3d  lea     r8d, [rdx+1]
0x14005ae41  call    _lseeki64_nolock
0x14005ae46  mov     r8, [rsp+98h+var_58]
0x14005ae4b  lea     r11, qword_140195270
0x14005ae52  mov     r10b, [rsp+98h+arg_0]
0x14005ae5a  mov     edx, 1
0x14005ae5f  mov     rcx, [r11+r8*8]
0x14005ae63  mov     [rcx+r14*8+30h], rax
0x14005ae68  mov     rax, [r11+r8*8]
0x14005ae6c  mov     edi, esi
0x14005ae6e  mov     [rsp+98h+var_48], r15
0x14005ae73  mov     r9d, 0Ah
0x14005ae79  test    byte ptr [rax+r14*8+38h], 48h
0x14005ae7f  jz      short loc_14005AEFA
0x14005ae81  mov     al, [rax+r14*8+3Ah]
0x14005ae86  cmp     al, r9b
0x14005ae89  jz      short loc_14005AEFA
0x14005ae8b  test    ebp, ebp
0x14005ae8d  jz      short loc_14005AEFA
0x14005ae8f  mov     [r15], al
0x14005ae92  dec     ebp
0x14005ae94  mov     rax, [r11+r8*8]
0x14005ae98  add     r15, rdx
0x14005ae9b  mov     edi, edx
0x14005ae9d  mov     [rax+r14*8+3Ah], r9b
0x14005aea2  test    r10b, r10b
0x14005aea5  jz      short loc_14005AEFA
0x14005aea7  mov     rax, [r11+r8*8]
0x14005aeab  mov     cl, [rax+r14*8+3Bh]
0x14005aeb0  cmp     cl, r9b
0x14005aeb3  jz      short loc_14005AEFA
0x14005aeb5  test    ebp, ebp
0x14005aeb7  jz      short loc_14005AEFA
0x14005aeb9  mov     [r15], cl
0x14005aebc  lea     edi, [r9-8]
0x14005aec0  mov     rax, [r11+r8*8]
0x14005aec4  add     r15, rdx
0x14005aec7  dec     ebp
0x14005aec9  mov     [rax+r14*8+3Bh], r9b
0x14005aece  cmp     r10b, dl
0x14005aed1  jnz     short loc_14005AEFA
0x14005aed3  mov     rax, [r11+r8*8]
0x14005aed7  mov     cl, [rax+r14*8+3Ch]
0x14005aedc  cmp     cl, r9b
0x14005aedf  jz      short loc_14005AEFA
0x14005aee1  test    ebp, ebp
0x14005aee3  jz      short loc_14005AEFA
0x14005aee5  mov     [r15], cl
0x14005aee8  lea     edi, [r9-7]
0x14005aeec  mov     rax, [r11+r8*8]
0x14005aef0  add     r15, rdx
0x14005aef3  dec     ebp
0x14005aef5  mov     [rax+r14*8+3Ch], r9b
0x14005aefa  mov     ecx, r13d; FileHandle
0x14005aefd  mov     [rsp+98h+Mode], esi
0x14005af01  call    _isatty
0x14005af06  test    eax, eax
0x14005af08  jz      loc_14005AF99
0x14005af0e  mov     rax, [rsp+98h+var_58]
0x14005af13  lea     rcx, qword_140195270
0x14005af1a  mov     rax, [rcx+rax*8]
0x14005af1e  cmp     [rax+r14*8+38h], sil
0x14005af23  jge     short loc_14005AF99
0x14005af25  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleHandle
0x14005af2a  lea     rdx, [rsp+98h+Mode]; lpMode
0x14005af2f  call    cs:GetConsoleMode
0x14005af35  test    eax, eax
0x14005af37  jz      short loc_14005AF99
0x14005af39  cmp     [rsp+98h+arg_0], 2
0x14005af41  jnz     short loc_14005AF9E
0x14005af43  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleInput
0x14005af48  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfCharsRead
0x14005af50  shr     ebp, 1
0x14005af52  mov     rdx, r15; lpBuffer
0x14005af55  mov     r8d, ebp; nNumberOfCharsToRead
0x14005af58  mov     [rsp+98h+NumberOfCharsRead], esi
0x14005af5f  mov     [rsp+98h+pInputControl], rsi; pInputControl
0x14005af64  call    cs:ReadConsoleW
0x14005af6a  test    eax, eax
0x14005af6c  jnz     short loc_14005AF8D
0x14005af6e  call    cs:GetLastError
0x14005af74  mov     ecx, eax
0x14005af76  call    sub_14004ED80
0x14005af7b  or      edi, 0FFFFFFFFh
0x14005af7e  mov     rcx, rbx; Block
0x14005af81  call    _free_base
0x14005af86  mov     eax, edi
0x14005af88  jmp     loc_14005B113
0x14005af8d  mov     eax, [rsp+98h+NumberOfCharsRead]
0x14005af94  lea     edi, [rdi+rax*2]
0x14005af97  jmp     short loc_14005AFE0
0x14005af99  mov     byte ptr [rsp+98h+var_50], sil
0x14005af9e  mov     rcx, [rsp+98h+hConsoleHandle]; hFile
0x14005afa3  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfBytesRead
0x14005afab  mov     r8d, ebp; nNumberOfBytesToRead
0x14005afae  mov     [rsp+98h+NumberOfCharsRead], esi
0x14005afb5  mov     rdx, r15; lpBuffer
0x14005afb8  mov     [rsp+98h+pInputControl], rsi; lpOverlapped
0x14005afbd  call    cs:ReadFile
0x14005afc3  test    eax, eax
0x14005afc5  jz      loc_14005B0BF
0x14005afcb  cmp     [rsp+98h+NumberOfCharsRead], r12d
0x14005afd3  ja      loc_14005B0BF
0x14005afd9  add     edi, [rsp+98h+NumberOfCharsRead]
0x14005afe0  mov     rdx, [rsp+98h+var_58]
0x14005afe5  lea     r11, qword_140195270
0x14005afec  mov     rax, [r11+rdx*8]
0x14005aff0  cmp     [rax+r14*8+38h], sil
0x14005aff5  jge     short loc_14005AF7E
0x14005aff7  cmp     [rsp+98h+arg_0], 2
0x14005afff  movsxd  r8, edi
0x14005b002  jz      short loc_14005B029
0x14005b004  mov     r9, [rsp+98h+arg_8]
0x14005b00c  mov     rax, r12
0x14005b00f  shr     rax, 1
0x14005b012  mov     rdx, r15
0x14005b015  mov     ecx, r13d
0x14005b018  mov     [rsp+98h+pInputControl], rax
0x14005b01d  call    sub_14005A87C
0x14005b022  mov     edi, eax
0x14005b024  jmp     loc_14005AF7E
0x14005b029  shr     r8, 1
0x14005b02c  cmp     byte ptr [rsp+98h+var_50], sil
0x14005b031  jz      short loc_14005B0AD
0x14005b033  mov     r10, [rsp+98h+var_48]
0x14005b038  mov     rax, r10
0x14005b03b  mov     rdi, r10
0x14005b03e  lea     r9, [r10+r8*2]
0x14005b042  cmp     r10, r9
0x14005b045  jnb     short loc_14005B0A0
0x14005b047  mov     esi, 0Ah
0x14005b04c  movzx   ecx, word ptr [rax]
0x14005b04f  cmp     cx, 1Ah
0x14005b053  jz      short loc_14005B08F
0x14005b055  cmp     cx, 0Dh
0x14005b059  jnz     short loc_14005B075
0x14005b05b  lea     r8, [rax+2]
0x14005b05f  cmp     r8, r9
0x14005b062  jnb     short loc_14005B075
0x14005b064  cmp     [r8], si
0x14005b068  jnz     short loc_14005B075
0x14005b06a  movzx   ecx, si
0x14005b06d  mov     r11d, 4
0x14005b073  jmp     short loc_14005B07B
0x14005b075  mov     r11d, 2
0x14005b07b  add     rax, r11
0x14005b07e  mov     [rdi], cx
0x14005b081  lea     r8, [rdi+2]
0x14005b085  mov     rdi, r8
0x14005b088  cmp     rax, r9
0x14005b08b  jb      short loc_14005B04C
0x14005b08d  jmp     short loc_14005B0A0
0x14005b08f  lea     rcx, qword_140195270
0x14005b096  mov     rax, [rcx+rdx*8]
0x14005b09a  or      byte ptr [rax+r14*8+38h], 2
0x14005b0a0  sub     rdi, r10
0x14005b0a3  sar     rdi, 1
0x14005b0a6  add     edi, edi
0x14005b0a8  jmp     loc_14005AF7E
0x14005b0ad  mov     rdx, [rsp+98h+var_48]
0x14005b0b2  mov     ecx, r13d
0x14005b0b5  call    sub_14005A680
0x14005b0ba  jmp     loc_14005B022
0x14005b0bf  call    cs:GetLastError
0x14005b0c5  cmp     eax, 5
0x14005b0c8  jnz     short loc_14005B0E5
0x14005b0ca  call    sub_14004EDF0
0x14005b0cf  mov     dword ptr [rax], 9
0x14005b0d5  call    sub_14004EDCC
0x14005b0da  mov     dword ptr [rax], 5
0x14005b0e0  jmp     loc_14005AF7B
0x14005b0e5  cmp     eax, 6Dh ; 'm'
0x14005b0e8  jnz     loc_14005AF74
0x14005b0ee  mov     edi, esi
0x14005b0f0  jmp     loc_14005AF7E
0x14005b0f5  xor     eax, eax
0x14005b0f7  jmp     short loc_14005B113
0x14005b0f9  call    sub_14004EDCC
0x14005b0fe  mov     [rax], esi
0x14005b100  call    sub_14004EDF0
0x14005b105  mov     dword ptr [rax], 9
0x14005b10b  call    _invalid_parameter_noinfo
0x14005b110  or      eax, 0FFFFFFFFh
0x14005b113  mov     rbx, [rsp+98h+arg_10]
0x14005b11b  add     rsp, 60h
0x14005b11f  pop     r15
0x14005b121  pop     r14
0x14005b123  pop     r13
0x14005b125  pop     r12
0x14005b127  pop     rdi
0x14005b128  pop     rsi
0x14005b129  pop     rbp
0x14005b12a  retn
```
