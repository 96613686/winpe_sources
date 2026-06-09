# MpPluginCheckExclusion_0

- ea: `0x18004a9c0`
- end: `0x18004addd`
- name: `MpPluginCheckExclusion_0`
- size: `1053`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a4c0`
- `0x180069c28`
- `0x1800c7bd4`

## callees

- `0x1800115a0`
- `0x18003d758`
- `0x18003d86c`
- `0x180040a58`
- `0x18004a9c0`
- `0x18008630c`
- `0x180086770`
- `0x1800d4220`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18004ac6e`
- `ntdll!RtlCompareUnicodeString` at `0x18004ac6e`

## pseudocode

```c
__int64 __fastcall MpPluginCheckExclusion_0(WCHAR *a1, _DWORD *a2)
{
  __int64 v4; // r8
  WCHAR *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // r14d
  _BYTE *v14; // r10
  unsigned __int64 v15; // r13
  WCHAR *v16; // r15
  bool v17; // zf
  __int64 v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rsi
  unsigned __int64 v24; // rax
  WCHAR *v25; // r15
  UNICODE_STRING String2; // [rsp+40h] [rbp-40h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v31; // [rsp+70h] [rbp-10h]

  *a2 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
LABEL_56:
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 50, &stru_1800ED6B8, v6);
    return v6;
  }
  v4 = 0x3FFFFFFF;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? 0x80070057 : 0;
  if ( !v4 )
    goto LABEL_56;
  v7 = 2 * (0x3FFFFFFF - v4);
  v8 = -v4;
  v9 = v7 & -(__int64)(v8 != 0);
  *(_QWORD *)&String2.Length = 0;
  sub_180086770((char *)lpMem + 120, &String2, v8);
  *(_QWORD *)&String1.Length = 0;
  sub_18008630C((char *)lpMem + 120, &String1);
  v10 = *(_QWORD *)&String2.Length;
  v11 = *(_QWORD *)&String1.Length;
  if ( *(_QWORD *)&String1.Length )
  {
    v31 = 0;
    v30[0] = *(_QWORD *)(*(_QWORD *)&String2.Length + 48LL);
    v30[1] = a1;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64))(*(_QWORD *)&String1.Length + 16LL))(
            *(_QWORD *)(*(_QWORD *)&String1.Length + 24LL),
            16465,
            v30,
            24);
    v13 = v12;
    if ( v12 >= 0 )
    {
      *a2 = v31;
      goto LABEL_28;
    }
    v14 = off_180119DF0;
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
    {
      sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 39, &stru_1800F6800, (unsigned int)v12);
      v14 = off_180119DF0;
    }
    v15 = v9;
    if ( v14 == (_BYTE *)&off_180119DF0 || (v14[28] & 0x10) == 0 )
      goto LABEL_15;
    sub_18003D758(*((_QWORD *)v14 + 2), 51, &stru_1800ED6B8, v13);
  }
  v14 = off_180119DF0;
  v15 = v9;
LABEL_15:
  v16 = *(WCHAR **)(*(_QWORD *)(*(_QWORD *)(v10 + 48) + 16LL) + 48LL);
  v17 = v16 == 0;
  while ( 1 )
  {
    if ( v17 || !*v16 )
    {
      *a2 = 0;
      goto LABEL_49;
    }
    v18 = 0x3FFFFFFF;
    v19 = v16;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    v13 = v18 == 0 ? 0x80070057 : 0;
    if ( !v18 )
      break;
    v20 = 2 * (0x3FFFFFFF - v18);
    v21 = -v18;
    v22 = v20 & -(__int64)(v21 != 0);
    if ( v22 > v15 )
      goto LABEL_38;
    String1 = 0;
    String2 = 0;
    if ( v22 <= 0xFFFF )
    {
      String1.Length = v21 != 0 ? v20 : 0;
      String1.MaximumLength = String1.Length;
      String1.Buffer = a1;
      String2.Length = String1.Length;
      String2.MaximumLength = String1.Length;
      String2.Buffer = v16;
      if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
        goto LABEL_37;
      v24 = (unsigned __int64)(unsigned __int16)v22 >> 1;
      if ( String1.Buffer[v24] != 92 && String1.Buffer[v24] && String1.Buffer[v24 - 1] != 92 )
        goto LABEL_37;
      if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 4) != 0 )
        sub_18003D86C(
          *((_QWORD *)off_180119DF0 + 2),
          54,
          (unsigned int)&stru_1800ED6B8,
          String1.Buffer,
          (__int64)String2.Buffer);
      *a2 = 1;
LABEL_49:
      if ( v11 && _InterlockedDecrement((volatile signed __int32 *)(v11 + 8)) <= 0 )
      {
        _mm_lfence();
        (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
      }
      if ( _InterlockedDecrement((volatile signed __int32 *)(v10 + 8)) <= 0 )
      {
        _mm_lfence();
        (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
      }
      return 0;
    }
    if ( v14 != (_BYTE *)&off_180119DF0 && (v14[28] & 2) != 0 )
    {
      sub_180040A58(*((_QWORD *)v14 + 2), 53, &stru_1800ED6B8, v20 & -(__int64)(v21 != 0));
LABEL_37:
      v14 = off_180119DF0;
    }
LABEL_38:
    v25 = &v16[v22 >> 1];
    v17 = v25 + 1 == 0;
    v16 = v25 + 1;
  }
  if ( v14 != (_BYTE *)&off_180119DF0 && (v14[28] & 1) != 0 )
    sub_18003D758(*((_QWORD *)v14 + 2), 52, &stru_1800ED6B8, v13);
  if ( v11 )
  {
LABEL_28:
    if ( _InterlockedDecrement((volatile signed __int32 *)(v11 + 8)) <= 0 )
    {
      _mm_lfence();
      (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    }
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)(v10 + 8)) <= 0 )
  {
    _mm_lfence();
    (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
  }
  return v13;
}

```

## disassembly

```asm
0x18004a9c0  mov     [rsp-38h+arg_10], rbx
0x18004a9c5  push    rbp
0x18004a9c6  push    rsi
0x18004a9c7  push    rdi
0x18004a9c8  push    r12
0x18004a9ca  push    r13
0x18004a9cc  push    r14
0x18004a9ce  push    r15
0x18004a9d0  mov     rbp, rsp
0x18004a9d3  sub     rsp, 80h
0x18004a9da  mov     rax, cs:__security_cookie
0x18004a9e1  xor     rax, rsp
0x18004a9e4  mov     [rbp+var_8], rax
0x18004a9e8  mov     r15, rdx
0x18004a9eb  mov     [rbp+var_50], rdx
0x18004a9ef  mov     r14, rcx
0x18004a9f2  mov     [rbp+var_48], rcx
0x18004a9f6  xor     r13d, r13d
0x18004a9f9  mov     [rdx], r13d
0x18004a9fc  test    rcx, rcx
0x18004a9ff  jz      loc_18004AD7E
0x18004aa05  mov     ecx, 3FFFFFFFh
0x18004aa0a  mov     r8d, ecx
0x18004aa0d  mov     rax, r14
0x18004aa10  cmp     [rax], r13w
0x18004aa14  jz      short loc_18004AA20
0x18004aa16  add     rax, 2
0x18004aa1a  sub     r8, 1
0x18004aa1e  jnz     short loc_18004AA10
0x18004aa20  mov     rax, r8
0x18004aa23  neg     rax
0x18004aa26  sbb     ebx, ebx
0x18004aa28  not     ebx
0x18004aa2a  and     ebx, 80070057h
0x18004aa30  test    r8, r8
0x18004aa33  jz      loc_18004AD83
0x18004aa39  mov     rax, rcx
0x18004aa3c  sub     rax, r8
0x18004aa3f  add     rax, rax
0x18004aa42  neg     r8
0x18004aa45  sbb     rsi, rsi
0x18004aa48  and     rsi, rax
0x18004aa4b  mov     qword ptr [rbp+String2.Length], r13
0x18004aa4f  mov     rcx, cs:lpMem
0x18004aa56  add     rcx, 78h ; 'x'
0x18004aa5a  lea     rdx, [rbp+String2]
0x18004aa5e  call    sub_180086770
0x18004aa63  mov     qword ptr [rbp+String1.Length], r13
0x18004aa67  mov     rcx, cs:lpMem
0x18004aa6e  add     rcx, 78h ; 'x'
0x18004aa72  lea     rdx, [rbp+String1]
0x18004aa76  call    sub_18008630C
0x18004aa7b  lea     r12, off_180119DF0
0x18004aa82  mov     rdi, qword ptr [rbp+String2.Length]
0x18004aa86  mov     rbx, qword ptr [rbp+String1.Length]
0x18004aa8a  test    rbx, rbx
0x18004aa8d  jz      loc_18004AB24
0x18004aa93  mov     [rbp+var_10], r13
0x18004aa97  mov     rax, [rdi+30h]
0x18004aa9b  mov     [rbp+var_20], rax
0x18004aa9f  mov     [rbp+var_18], r14
0x18004aaa3  mov     r9d, 18h
0x18004aaa9  lea     r8, [rbp+var_20]
0x18004aaad  mov     edx, 4051h
0x18004aab2  mov     rcx, [rbx+18h]
0x18004aab6  mov     rax, [rbx+10h]
0x18004aaba  call    cs:__guard_dispatch_icall_fptr
0x18004aac0  mov     r14d, eax
0x18004aac3  test    eax, eax
0x18004aac5  jns     loc_18004ABED
0x18004aacb  mov     r10, cs:off_180119DF0
0x18004aad2  cmp     r10, r12
0x18004aad5  jz      short loc_18004AAFD
0x18004aad7  test    byte ptr [r10+1Ch], 1
0x18004aadc  jz      short loc_18004AAFD
0x18004aade  mov     edx, 27h ; '''
0x18004aae3  mov     r9d, eax
0x18004aae6  lea     r8, stru_1800F6800
0x18004aaed  mov     rcx, [r10+10h]
0x18004aaf1  call    sub_18003D758
0x18004aaf6  mov     r10, cs:off_180119DF0
0x18004aafd  mov     r13, rsi
0x18004ab00  cmp     r10, r12
0x18004ab03  jz      short loc_18004AB2E
0x18004ab05  test    byte ptr [r10+1Ch], 10h
0x18004ab0a  jz      short loc_18004AB2E
0x18004ab0c  mov     edx, 33h ; '3'
0x18004ab11  mov     r9d, r14d
0x18004ab14  lea     r8, stru_1800ED6B8
0x18004ab1b  mov     rcx, [r10+10h]
0x18004ab1f  call    sub_18003D758
0x18004ab24  mov     r10, cs:off_180119DF0
0x18004ab2b  mov     r13, rsi
0x18004ab2e  mov     rax, [rdi+30h]
0x18004ab32  mov     rcx, [rax+10h]
0x18004ab36  mov     r15, [rcx+30h]
0x18004ab3a  xor     edx, edx
0x18004ab3c  test    r15, r15
0x18004ab3f  jz      loc_18004AD25
0x18004ab45  cmp     [r15], dx
0x18004ab49  jz      loc_18004AD25
0x18004ab4f  mov     ecx, 3FFFFFFFh
0x18004ab54  mov     rax, r15
0x18004ab57  cmp     [rax], dx
0x18004ab5a  jz      short loc_18004AB66
0x18004ab5c  add     rax, 2
0x18004ab60  sub     rcx, 1
0x18004ab64  jnz     short loc_18004AB57
0x18004ab66  mov     rax, rcx
0x18004ab69  neg     rax
0x18004ab6c  sbb     r14d, r14d
0x18004ab6f  not     r14d
0x18004ab72  and     r14d, 80070057h
0x18004ab79  test    rcx, rcx
0x18004ab7c  jz      loc_18004ACEF
0x18004ab82  mov     eax, 3FFFFFFFh
0x18004ab87  sub     rax, rcx
0x18004ab8a  add     rax, rax
0x18004ab8d  neg     rcx
0x18004ab90  sbb     rsi, rsi
0x18004ab93  and     rsi, rax
0x18004ab96  cmp     rsi, r13
0x18004ab99  ja      loc_18004ACA3
0x18004ab9f  xorps   xmm0, xmm0
0x18004aba2  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18004aba6  xorps   xmm1, xmm1
0x18004aba9  movups  xmmword ptr [rbp+String2.Length], xmm1
0x18004abad  cmp     rsi, 0FFFFh
0x18004abb4  jbe     loc_18004AC47
0x18004abba  cmp     r10, r12
0x18004abbd  jz      loc_18004ACA3
0x18004abc3  test    byte ptr [r10+1Ch], 2
0x18004abc8  jz      loc_18004ACA3
0x18004abce  mov     edx, 35h ; '5'
0x18004abd3  mov     r9, rsi
0x18004abd6  lea     r8, stru_1800ED6B8
0x18004abdd  mov     rcx, [r10+10h]
0x18004abe1  call    sub_180040A58
0x18004abe6  xor     edx, edx
0x18004abe8  jmp     loc_18004AC9C
0x18004abed  mov     eax, dword ptr [rbp+var_10]
0x18004abf0  mov     [r15], eax
0x18004abf3  or      esi, 0FFFFFFFFh
0x18004abf6  mov     eax, esi
0x18004abf8  lock xadd [rbx+8], eax
0x18004abfd  add     eax, esi
0x18004abff  test    eax, eax
0x18004ac01  jg      short loc_18004AC1B
0x18004ac03  lfence
0x18004ac06  mov     rax, [rbx]
0x18004ac09  mov     edx, 1
0x18004ac0e  mov     rcx, rbx
0x18004ac11  mov     rax, [rax]
0x18004ac14  call    cs:__guard_dispatch_icall_fptr
0x18004ac1a  nop
0x18004ac1b  mov     eax, esi
0x18004ac1d  lock xadd [rdi+8], eax
0x18004ac22  add     eax, esi
0x18004ac24  test    eax, eax
0x18004ac26  jg      short loc_18004AC3F
0x18004ac28  lfence
0x18004ac2b  mov     rax, [rdi]
0x18004ac2e  mov     edx, 1
0x18004ac33  mov     rcx, rdi
0x18004ac36  mov     rax, [rax]
0x18004ac39  call    cs:__guard_dispatch_icall_fptr
0x18004ac3f  mov     eax, r14d
0x18004ac42  jmp     loc_18004ADB6
0x18004ac47  mov     [rbp+String1.Length], si
0x18004ac4b  mov     [rbp+String1.MaximumLength], si
0x18004ac4f  mov     rax, [rbp+var_48]
0x18004ac53  mov     [rbp+String1.Buffer], rax
0x18004ac57  mov     [rbp+String2.Length], si
0x18004ac5b  mov     [rbp+String2.MaximumLength], si
0x18004ac5f  mov     [rbp+String2.Buffer], r15
0x18004ac63  mov     r8b, 1; CaseInsensitive
0x18004ac66  lea     rdx, [rbp+String2]; String2
0x18004ac6a  lea     rcx, [rbp+String1]; String1
0x18004ac6e  call    cs:RtlCompareUnicodeString
0x18004ac74  xor     edx, edx
0x18004ac76  test    eax, eax
0x18004ac78  jnz     short loc_18004AC9C
0x18004ac7a  movzx   eax, si
0x18004ac7d  shr     rax, 1
0x18004ac80  mov     r9, [rbp+String1.Buffer]
0x18004ac84  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x18004ac8a  jz      short loc_18004ACB3
0x18004ac8c  cmp     [r9+rax*2], dx
0x18004ac91  jz      short loc_18004ACB3
0x18004ac93  cmp     word ptr [r9+rax*2-2], 5Ch ; '\'
0x18004ac9a  jz      short loc_18004ACB3
0x18004ac9c  mov     r10, cs:off_180119DF0
0x18004aca3  shr     rsi, 1
0x18004aca6  lea     r15, [r15+rsi*2]
0x18004acaa  add     r15, 2
0x18004acae  jmp     loc_18004AB3F
0x18004acb3  mov     rcx, cs:off_180119DF0
0x18004acba  cmp     rcx, r12
0x18004acbd  jz      short loc_18004ACE3
0x18004acbf  test    byte ptr [rcx+1Ch], 4
0x18004acc3  jz      short loc_18004ACE3
0x18004acc5  mov     edx, 36h ; '6'
0x18004acca  mov     rax, [rbp+String2.Buffer]
0x18004acce  mov     [rsp+80h+var_60], rax
0x18004acd3  lea     r8, stru_1800ED6B8
0x18004acda  mov     rcx, [rcx+10h]
0x18004acde  call    sub_18003D86C
0x18004ace3  mov     rax, [rbp+var_50]
0x18004ace7  mov     dword ptr [rax], 1
0x18004aced  jmp     short loc_18004AD2B
0x18004acef  cmp     r10, r12
0x18004acf2  jz      short loc_18004AD14
0x18004acf4  test    byte ptr [r10+1Ch], 1
0x18004acf9  jz      short loc_18004AD14
0x18004acfb  mov     edx, 34h ; '4'
0x18004ad00  mov     r9d, r14d
0x18004ad03  lea     r8, stru_1800ED6B8
0x18004ad0a  mov     rcx, [r10+10h]
0x18004ad0e  call    sub_18003D758
0x18004ad13  nop
0x18004ad14  or      esi, 0FFFFFFFFh
0x18004ad17  test    rbx, rbx
0x18004ad1a  jz      loc_18004AC1B
0x18004ad20  jmp     loc_18004ABF6
0x18004ad25  mov     rax, [rbp+var_50]
0x18004ad29  mov     [rax], edx
0x18004ad2b  or      esi, 0FFFFFFFFh
0x18004ad2e  test    rbx, rbx
0x18004ad31  jz      short loc_18004AD56
0x18004ad33  mov     eax, esi
0x18004ad35  lock xadd [rbx+8], eax
0x18004ad3a  add     eax, esi
0x18004ad3c  test    eax, eax
0x18004ad3e  jg      short loc_18004AD56
0x18004ad40  lfence
0x18004ad43  mov     rax, [rbx]
0x18004ad46  lea     edx, [rsi+2]
0x18004ad49  mov     rcx, rbx
0x18004ad4c  mov     rax, [rax]
0x18004ad4f  call    cs:__guard_dispatch_icall_fptr
0x18004ad55  nop
0x18004ad56  mov     eax, esi
0x18004ad58  lock xadd [rdi+8], eax
0x18004ad5d  add     eax, esi
0x18004ad5f  test    eax, eax
0x18004ad61  jg      short loc_18004AD7A
0x18004ad63  lfence
0x18004ad66  mov     rax, [rdi]
0x18004ad69  mov     edx, 1
0x18004ad6e  mov     rcx, rdi
0x18004ad71  mov     rax, [rax]
0x18004ad74  call    cs:__guard_dispatch_icall_fptr
0x18004ad7a  xor     eax, eax
0x18004ad7c  jmp     short loc_18004ADB6
0x18004ad7e  mov     ebx, 80070057h
0x18004ad83  lea     r12, off_180119DF0
0x18004ad8a  mov     rcx, cs:off_180119DF0
0x18004ad91  cmp     rcx, r12
0x18004ad94  jz      short loc_18004ADB4
0x18004ad96  test    byte ptr [rcx+1Ch], 1
0x18004ad9a  jz      short loc_18004ADB4
0x18004ad9c  mov     edx, 32h ; '2'
0x18004ada1  mov     r9d, ebx
0x18004ada4  lea     r8, stru_1800ED6B8
0x18004adab  mov     rcx, [rcx+10h]
0x18004adaf  call    sub_18003D758
0x18004adb4  mov     eax, ebx
0x18004adb6  mov     rcx, [rbp+var_8]
0x18004adba  xor     rcx, rsp; StackCookie
0x18004adbd  call    __security_check_cookie
0x18004adc2  mov     rbx, [rsp+80h+arg_10]
0x18004adca  add     rsp, 80h
0x18004add1  pop     r15
0x18004add3  pop     r14
0x18004add5  pop     r13
0x18004add7  pop     r12
0x18004add9  pop     rdi
0x18004adda  pop     rsi
0x18004addb  pop     rbp
0x18004addc  retn
```
