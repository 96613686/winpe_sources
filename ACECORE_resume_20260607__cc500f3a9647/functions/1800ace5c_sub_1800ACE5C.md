# sub_1800ACE5C

- ea: `0x1800ace5c`
- end: `0x1800ad3b1`
- name: `sub_1800ACE5C`
- size: `1365`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x1800bbb18`
- `0x1800bbd7c`
- `0x1800bc024`

## callees

- `0x180073d5c`
- `0x180073ea8`
- `0x180073ef4`
- `0x180087ce0`
- `0x180098e08`
- `0x180098e44`
- `0x1800ace5c`
- `0x1800b8420`
- `0x1800bccb4`
- `0x1800cad3c`
- `0x1800cb388`
- `0x1800cc710`
- `0x1800cca28`
- `0x1800d0dac`
- `0x1801d6c50`

## import_xrefs

- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800acf75`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800ad07d`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800ad138`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800acf75`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800ad07d`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800ad138`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800acff3`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800ad1d7`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800acff3`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800ad1d7`

## string_xrefs

- `0x1800ad2bd`: `DateCreate`
- `0x1800ad2d9`: `DateCreate`
- `0x1800ad2ee`: `DateUpdate`
- `0x1800ad30a`: `DateUpdate`

## pseudocode

```c
__int64 __fastcall sub_1800ACE5C(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  int v8; // r14d
  __int64 v9; // rax
  unsigned int v10; // edx
  unsigned int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // edx
  _DWORD *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // r9d
  int v25; // ebp
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // eax
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // r8
  __int64 v40; // r9
  int v41; // eax
  __int64 v42; // r8
  __int64 v43; // r9
  int v44; // eax
  __int64 v45; // r8
  __int64 v46; // r9
  int v47; // eax
  __int64 v48; // r8
  __int64 v49; // r9
  int v50; // eax

  sub_180073D5C(a1, 50, a4);
  *(_QWORD *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 24) = a3;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = -1;
  *(_DWORD *)(a1 + 60) = -1;
  *(_DWORD *)(a1 + 64) = -1;
  *(_DWORD *)(a1 + 68) = -1;
  *(_DWORD *)(a1 + 72) = -1;
  *(_DWORD *)(a1 + 76) = -1;
  *(_DWORD *)(a1 + 80) = -1;
  *(_DWORD *)(a1 + 84) = -1;
  *(_DWORD *)(a1 + 96) = 1;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  v8 = 0;
  if ( (*a4 & 8) != 0 )
    return a1;
  sub_180073EA8(a2 + 168, a1, a4);
  if ( (*a4 & 8) != 0 )
    return a1;
  *(_QWORD *)(a1 + 88) = sub_1800BCCB4(a2, a3, a4);
  v9 = *(_QWORD *)(a1 + 24);
  if ( *(_DWORD *)(v9 + 120) != 1 )
  {
    if ( (*a4 & 8) != 0 )
    {
LABEL_76:
      sub_180073EF4(a2 + 168, a1);
      return a1;
    }
    if ( *(_DWORD *)(a3 + 148) == 2 )
      goto LABEL_25;
    v10 = 0;
    v11 = *(_DWORD *)(v9 + 100);
    if ( v11 )
    {
      while ( 1 )
      {
        v12 = *(_QWORD *)(*(_QWORD *)(v9 + 88) + 8LL * v10);
        if ( *(_DWORD *)(v12 + 56) == *(_DWORD *)(v9 + 644) )
          break;
        if ( ++v10 >= v11 )
          goto LABEL_9;
      }
    }
    else
    {
LABEL_9:
      v12 = 0;
    }
    *(_QWORD *)(a1 + 112) = v12;
    if ( v12 )
    {
      sub_1800CCA28(v12, *(_QWORD *)(a1 + 16), 1);
    }
    else
    {
      v13 = Mso20Win32Client_52497(3432, 2);
      if ( v13 )
        v14 = sub_1800CAD3C(v13, *(_QWORD *)(a1 + 24), a4);
      else
        v14 = 0;
      *(_QWORD *)(a1 + 112) = v14;
      if ( !v14 )
        sub_180098E08(a4, 4294966285LL);
      if ( (*a4 & 8) != 0 )
        goto LABEL_25;
      sub_1800CC710(*(_QWORD *)(a1 + 112), a1, *(_DWORD *)(*(_QWORD *)(a1 + 24) + 644LL), 1, (__int64)a4);
      if ( (*a4 & 8) != 0 )
      {
        v15 = *(_QWORD *)(a1 + 112);
        if ( v15 )
        {
          sub_1800CB388(*(_QWORD *)(a1 + 112));
          Mso20Win32Client_53248(v15);
        }
        *(_QWORD *)(a1 + 112) = 0;
        if ( (*a4 & 8) != 0 )
          goto LABEL_25;
      }
      v16 = *(_QWORD *)(a1 + 112);
      sub_1800B8420(v16, L"MSysACEs", 0x10u);
      *(_DWORD *)(v16 + 80) = 0;
    }
    if ( (*a4 & 8) == 0 )
      ++*(_DWORD *)(*(_QWORD *)(a1 + 112) + 92LL);
LABEL_25:
    v17 = *(_QWORD *)(a1 + 24);
    v18 = 0;
    v19 = *(_DWORD *)(v17 + 100);
    if ( v19 )
    {
      while ( 1 )
      {
        v20 = *(_DWORD **)(*(_QWORD *)(v17 + 88) + 8LL * v18);
        if ( v20[14] == *(_DWORD *)(v17 + 640) )
          break;
        if ( ++v18 >= v19 )
          goto LABEL_28;
      }
    }
    else
    {
LABEL_28:
      v20 = 0;
    }
    if ( v20 )
    {
      sub_1800CCA28(v20, *(_QWORD *)(a1 + 16), 1);
    }
    else
    {
      v21 = Mso20Win32Client_52497(3432, 2);
      if ( v21 )
        v20 = (_DWORD *)sub_1800CAD3C(v21, *(_QWORD *)(a1 + 24), a4);
      else
        v20 = 0;
      if ( v20 )
        v8 = 1;
      else
        sub_180098E08(a4, 4294966285LL);
      if ( (*a4 & 8) == 0 )
      {
        v24 = 6;
        if ( *(_DWORD *)(a3 + 148) != 2 )
          v24 = 1;
        sub_1800CC710((_DWORD)v20, a1, *(_DWORD *)(*(_QWORD *)(a1 + 24) + 640LL), v24, (__int64)a4);
        if ( (*a4 & 8) == 0 )
        {
          sub_1800B8420((__int64)v20, L"MSysObjects", 0x16u);
          v20[20] = 0;
        }
      }
    }
    v25 = v8;
    if ( (*a4 & 8) == 0 )
    {
      v26 = Mso20Win32Client_52497(656, 2);
      if ( v26 )
        v27 = sub_180087CE0(v26, a1, (__int64)v20, 1, 1, (__int64)a4, 0, 0);
      else
        v27 = 0;
      *(_QWORD *)(a1 + 32) = v27;
      if ( v27 )
      {
        if ( (*a4 & 8) != 0 )
        {
          (**(void (__fastcall ***)(__int64, __int64))v27)(v27, 1);
          *(_QWORD *)(a1 + 32) = 0;
          v8 = 0;
          if ( v25 != 1 )
            v8 = v25;
        }
        else
        {
          *(_DWORD *)(v27 + 144) = 0;
        }
      }
      else
      {
        sub_180098E08(a4, 4294966285LL);
      }
    }
    v28 = *(_DWORD *)a4;
    if ( (*(_DWORD *)a4 & 8) != 0 && v8 == 1 )
    {
      if ( v20[15] != 10 )
      {
        sub_1800CB388(v20);
        Mso20Win32Client_53248(v20);
        v28 = *(_DWORD *)a4;
      }
      v20 = 0;
    }
    if ( (v28 & 8) == 0 )
    {
      v29 = sub_1800D0DAC(v20, L"ParentId", v22, v23);
      *(_DWORD *)(a1 + 56) = v29;
      if ( v29 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"ParentId", 0);
      v32 = sub_1800D0DAC(v20, L"Id", v30, v31);
      *(_DWORD *)(a1 + 60) = v32;
      if ( v32 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"Id", 0);
      v35 = sub_1800D0DAC(v20, L"Name", v33, v34);
      *(_DWORD *)(a1 + 64) = v35;
      if ( v35 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"Name", 0);
      v38 = sub_1800D0DAC(v20, L"Type", v36, v37);
      *(_DWORD *)(a1 + 68) = v38;
      if ( v38 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"Type", 0);
      v41 = sub_1800D0DAC(v20, L"DateCreate", v39, v40);
      *(_DWORD *)(a1 + 72) = v41;
      if ( v41 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"DateCreate", 0);
      v44 = sub_1800D0DAC(v20, L"DateUpdate", v42, v43);
      *(_DWORD *)(a1 + 76) = v44;
      if ( v44 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"DateUpdate", 0);
      v47 = sub_1800D0DAC(v20, L"Owner", v45, v46);
      *(_DWORD *)(a1 + 80) = v47;
      if ( v47 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"Owner", 0);
      v50 = sub_1800D0DAC(v20, L"Flags", v48, v49);
      *(_DWORD *)(a1 + 84) = v50;
      if ( v50 == -1 )
        sub_180098E44((_DWORD)a4, -1206, -8188, (unsigned int)L"Flags", 0);
    }
  }
  if ( (*a4 & 8) != 0 )
    goto LABEL_76;
  return a1;
}

```

## disassembly

```asm
0x1800ace5c  mov     [rsp+arg_10], rbx
0x1800ace61  mov     [rsp+arg_0], rcx
0x1800ace66  push    rbp
0x1800ace67  push    rsi
0x1800ace68  push    rdi
0x1800ace69  push    r12
0x1800ace6b  push    r13
0x1800ace6d  push    r14
0x1800ace6f  push    r15
0x1800ace71  sub     rsp, 40h
0x1800ace75  mov     rsi, r9
0x1800ace78  mov     rbp, r8
0x1800ace7b  mov     r15, rdx
0x1800ace7e  mov     rdi, rcx
0x1800ace81  mov     r8, r9
0x1800ace84  mov     edx, 32h ; '2'
0x1800ace89  call    sub_180073D5C
0x1800ace8e  mov     [rdi+10h], r15
0x1800ace92  mov     [rdi+18h], rbp
0x1800ace96  xor     r12d, r12d
0x1800ace99  mov     [rdi+20h], r12
0x1800ace9d  mov     [rdi+28h], r12
0x1800acea1  mov     [rdi+30h], r12
0x1800acea5  or      eax, 0FFFFFFFFh
0x1800acea8  mov     [rdi+38h], eax
0x1800aceab  mov     [rdi+3Ch], eax
0x1800aceae  mov     [rdi+40h], eax
0x1800aceb1  mov     [rdi+44h], eax
0x1800aceb4  mov     [rdi+48h], eax
0x1800aceb7  mov     [rdi+4Ch], eax
0x1800aceba  mov     [rdi+50h], eax
0x1800acebd  mov     [rdi+54h], eax
0x1800acec0  lea     r13d, [r12+1]
0x1800acec5  mov     [rdi+60h], r13d
0x1800acec9  mov     [rdi+58h], r12
0x1800acecd  mov     [rdi+68h], r12
0x1800aced1  mov     [rdi+70h], r12
0x1800aced5  mov     r14d, r12d
0x1800aced8  test    byte ptr [rsi], 8
0x1800acedb  jnz     loc_1800AD396
0x1800acee1  lea     rcx, [r15+0A8h]
0x1800acee8  mov     r8, rsi
0x1800aceeb  mov     rdx, rdi
0x1800aceee  call    sub_180073EA8
0x1800acef3  test    byte ptr [rsi], 8
0x1800acef6  jnz     loc_1800AD396
0x1800acefc  mov     r8, rsi
0x1800aceff  mov     rdx, rbp
0x1800acf02  mov     rcx, r15
0x1800acf05  call    sub_1800BCCB4
0x1800acf0a  mov     [rdi+58h], rax
0x1800acf0e  mov     rax, [rdi+18h]
0x1800acf12  cmp     [rax+78h], r13d
0x1800acf16  jz      loc_1800AD381
0x1800acf1c  test    byte ptr [rsi], 8
0x1800acf1f  jnz     loc_1800AD386
0x1800acf25  cmp     dword ptr [rbp+94h], 2
0x1800acf2c  jz      loc_1800AD03D
0x1800acf32  mov     r10d, [rax+284h]
0x1800acf39  mov     edx, r12d
0x1800acf3c  mov     r8d, [rax+64h]
0x1800acf40  test    r8d, r8d
0x1800acf43  jz      short loc_1800ACF5D
0x1800acf45  mov     r9, [rax+58h]
0x1800acf49  mov     eax, edx
0x1800acf4b  mov     rcx, [r9+rax*8]
0x1800acf4f  cmp     [rcx+38h], r10d
0x1800acf53  jz      short loc_1800ACF60
0x1800acf55  add     edx, r13d
0x1800acf58  cmp     edx, r8d
0x1800acf5b  jb      short loc_1800ACF49
0x1800acf5d  mov     rcx, r12
0x1800acf60  mov     [rdi+70h], rcx
0x1800acf64  test    rcx, rcx
0x1800acf67  jnz     loc_1800AD021
0x1800acf6d  lea     edx, [rcx+2]
0x1800acf70  mov     ecx, 0D68h
0x1800acf75  call    cs:Mso20Win32Client_52497
0x1800acf7b  mov     [rsp+78h+arg_8], rax
0x1800acf83  test    rax, rax
0x1800acf86  jz      short loc_1800ACF99
0x1800acf88  mov     r8, rsi
0x1800acf8b  mov     rdx, [rdi+18h]
0x1800acf8f  mov     rcx, rax
0x1800acf92  call    sub_1800CAD3C
0x1800acf97  jmp     short loc_1800ACF9C
0x1800acf99  mov     rax, r12
0x1800acf9c  mov     [rdi+70h], rax
0x1800acfa0  test    rax, rax
0x1800acfa3  jnz     short loc_1800ACFB2
0x1800acfa5  mov     edx, 0FFFFFC0Dh
0x1800acfaa  mov     rcx, rsi
0x1800acfad  call    sub_180098E08
0x1800acfb2  test    byte ptr [rsi], 8
0x1800acfb5  jnz     loc_1800AD03D
0x1800acfbb  mov     rax, [rdi+18h]
0x1800acfbf  mov     [rsp+78h+var_58], rsi
0x1800acfc4  mov     r9d, r13d
0x1800acfc7  mov     r8d, [rax+284h]
0x1800acfce  mov     rdx, rdi
0x1800acfd1  mov     rcx, [rdi+70h]
0x1800acfd5  call    sub_1800CC710
0x1800acfda  test    byte ptr [rsi], 8
0x1800acfdd  jz      short loc_1800AD002
0x1800acfdf  mov     rbx, [rdi+70h]
0x1800acfe3  test    rbx, rbx
0x1800acfe6  jz      short loc_1800ACFF9
0x1800acfe8  mov     rcx, rbx
0x1800acfeb  call    sub_1800CB388
0x1800acff0  mov     rcx, rbx
0x1800acff3  call    cs:Mso20Win32Client_53248
0x1800acff9  mov     [rdi+70h], r12
0x1800acffd  test    byte ptr [rsi], 8
0x1800ad000  jnz     short loc_1800AD03D
0x1800ad002  mov     rbx, [rdi+70h]
0x1800ad006  mov     r8d, 10h
0x1800ad00c  lea     rdx, aMsysaces_0; "MSysACEs"
0x1800ad013  mov     rcx, rbx
0x1800ad016  call    sub_1800B8420
0x1800ad01b  mov     [rbx+50h], r12d
0x1800ad01f  jmp     short loc_1800AD030
0x1800ad021  mov     r9, rsi
0x1800ad024  mov     r8d, r13d
0x1800ad027  mov     rdx, [rdi+10h]
0x1800ad02b  call    sub_1800CCA28
0x1800ad030  test    byte ptr [rsi], 8
0x1800ad033  jnz     short loc_1800AD03D
0x1800ad035  mov     rax, [rdi+70h]
0x1800ad039  add     [rax+5Ch], r13d
0x1800ad03d  mov     rax, [rdi+18h]
0x1800ad041  mov     r9d, [rax+280h]
0x1800ad048  mov     ecx, r12d
0x1800ad04b  mov     edx, [rax+64h]
0x1800ad04e  test    edx, edx
0x1800ad050  jz      short loc_1800AD069
0x1800ad052  mov     r8, [rax+58h]
0x1800ad056  mov     eax, ecx
0x1800ad058  mov     rbx, [r8+rax*8]
0x1800ad05c  cmp     [rbx+38h], r9d
0x1800ad060  jz      short loc_1800AD06C
0x1800ad062  add     ecx, r13d
0x1800ad065  cmp     ecx, edx
0x1800ad067  jb      short loc_1800AD056
0x1800ad069  mov     rbx, r12
0x1800ad06c  test    rbx, rbx
0x1800ad06f  jnz     loc_1800AD110
0x1800ad075  lea     edx, [rbx+2]
0x1800ad078  mov     ecx, 0D68h
0x1800ad07d  call    cs:Mso20Win32Client_52497
0x1800ad083  mov     [rsp+78h+arg_8], rax
0x1800ad08b  test    rax, rax
0x1800ad08e  jz      short loc_1800AD0A4
0x1800ad090  mov     r8, rsi
0x1800ad093  mov     rdx, [rdi+18h]
0x1800ad097  mov     rcx, rax
0x1800ad09a  call    sub_1800CAD3C
0x1800ad09f  mov     rbx, rax
0x1800ad0a2  jmp     short loc_1800AD0A7
0x1800ad0a4  mov     rbx, r12
0x1800ad0a7  test    rbx, rbx
0x1800ad0aa  jnz     short loc_1800AD0BB
0x1800ad0ac  mov     edx, 0FFFFFC0Dh
0x1800ad0b1  mov     rcx, rsi
0x1800ad0b4  call    sub_180098E08
0x1800ad0b9  jmp     short loc_1800AD0BE
0x1800ad0bb  mov     r14d, r13d
0x1800ad0be  test    byte ptr [rsi], 8
0x1800ad0c1  jnz     short loc_1800AD122
0x1800ad0c3  mov     r8, [rdi+18h]
0x1800ad0c7  mov     [rsp+78h+var_58], rsi
0x1800ad0cc  mov     rdx, rdi
0x1800ad0cf  mov     rcx, rbx
0x1800ad0d2  mov     r8d, [r8+280h]
0x1800ad0d9  cmp     dword ptr [rbp+94h], 2
0x1800ad0e0  mov     r9d, 6
0x1800ad0e6  jz      short loc_1800AD0EB
0x1800ad0e8  mov     r9d, r13d
0x1800ad0eb  call    sub_1800CC710
0x1800ad0f0  test    byte ptr [rsi], 8
0x1800ad0f3  jnz     short loc_1800AD122
0x1800ad0f5  mov     r8d, 16h
0x1800ad0fb  lea     rdx, aMsysobjects_0; "MSysObjects"
0x1800ad102  mov     rcx, rbx
0x1800ad105  call    sub_1800B8420
0x1800ad10a  mov     [rbx+50h], r12d
0x1800ad10e  jmp     short loc_1800AD122
0x1800ad110  mov     r9, rsi
0x1800ad113  mov     r8d, r13d
0x1800ad116  mov     rdx, [rdi+10h]
0x1800ad11a  mov     rcx, rbx
0x1800ad11d  call    sub_1800CCA28
0x1800ad122  mov     ebp, r14d
0x1800ad125  test    byte ptr [rsi], 8
0x1800ad128  jnz     loc_1800AD1BB
0x1800ad12e  mov     edx, 2
0x1800ad133  mov     ecx, 290h
0x1800ad138  call    cs:Mso20Win32Client_52497
0x1800ad13e  mov     [rsp+78h+arg_8], rax
0x1800ad146  test    rax, rax
0x1800ad149  jz      short loc_1800AD175
0x1800ad14b  mov     [rsp+78h+var_40], r12d
0x1800ad150  mov     [rsp+78h+var_48], r12d
0x1800ad155  mov     [rsp+78h+var_50], rsi
0x1800ad15a  mov     dword ptr [rsp+78h+var_58], r13d
0x1800ad15f  mov     r9d, r13d
0x1800ad162  mov     r8, rbx
0x1800ad165  mov     rdx, rdi
0x1800ad168  mov     rcx, rax
0x1800ad16b  call    sub_180087CE0
0x1800ad170  mov     rcx, rax
0x1800ad173  jmp     short loc_1800AD178
0x1800ad175  mov     rcx, r12
0x1800ad178  mov     [rdi+20h], rcx
0x1800ad17c  test    rcx, rcx
0x1800ad17f  jnz     short loc_1800AD190
0x1800ad181  mov     edx, 0FFFFFC0Dh
0x1800ad186  mov     rcx, rsi
0x1800ad189  call    sub_180098E08
0x1800ad18e  jmp     short loc_1800AD1BB
0x1800ad190  test    byte ptr [rsi], 8
0x1800ad193  jz      short loc_1800AD1B4
0x1800ad195  mov     rax, [rcx]
0x1800ad198  mov     edx, r13d
0x1800ad19b  mov     rax, [rax]
0x1800ad19e  call    cs:__guard_dispatch_icall_fptr
0x1800ad1a4  mov     [rdi+20h], r12
0x1800ad1a8  mov     r14d, r12d
0x1800ad1ab  cmp     ebp, r13d
0x1800ad1ae  cmovnz  r14d, ebp
0x1800ad1b2  jmp     short loc_1800AD1BB
0x1800ad1b4  mov     [rcx+90h], r12d
0x1800ad1bb  mov     eax, [rsi]
0x1800ad1bd  test    al, 8
0x1800ad1bf  jz      short loc_1800AD1E2
0x1800ad1c1  cmp     r14d, r13d
0x1800ad1c4  jnz     short loc_1800AD1E2
0x1800ad1c6  cmp     dword ptr [rbx+3Ch], 0Ah
0x1800ad1ca  jz      short loc_1800AD1DF
0x1800ad1cc  mov     rcx, rbx
0x1800ad1cf  call    sub_1800CB388
0x1800ad1d4  mov     rcx, rbx
0x1800ad1d7  call    cs:Mso20Win32Client_53248
0x1800ad1dd  mov     eax, [rsi]
0x1800ad1df  mov     rbx, r12
0x1800ad1e2  test    al, 8
0x1800ad1e4  jnz     loc_1800AD381
0x1800ad1ea  lea     rdx, aParentid; "ParentId"
0x1800ad1f1  mov     rcx, rbx
0x1800ad1f4  call    sub_1800D0DAC
0x1800ad1f9  mov     [rdi+38h], eax
0x1800ad1fc  mov     ebp, 0FFFFE004h
0x1800ad201  mov     r14d, 0FFFFFB4Ah
0x1800ad207  or      r13d, 0FFFFFFFFh
0x1800ad20b  cmp     eax, r13d
0x1800ad20e  jnz     short loc_1800AD22A
0x1800ad210  mov     [rsp+78h+var_58], r12
0x1800ad215  lea     r9, aParentid; "ParentId"
0x1800ad21c  mov     r8d, ebp
0x1800ad21f  mov     edx, r14d
0x1800ad222  mov     rcx, rsi
0x1800ad225  call    sub_180098E44
0x1800ad22a  lea     rdx, aId; "Id"
0x1800ad231  mov     rcx, rbx
0x1800ad234  call    sub_1800D0DAC
0x1800ad239  mov     [rdi+3Ch], eax
0x1800ad23c  cmp     eax, r13d
0x1800ad23f  jnz     short loc_1800AD25B
0x1800ad241  mov     [rsp+78h+var_58], r12
0x1800ad246  lea     r9, aId; "Id"
0x1800ad24d  mov     r8d, ebp
0x1800ad250  mov     edx, r14d
0x1800ad253  mov     rcx, rsi
0x1800ad256  call    sub_180098E44
0x1800ad25b  lea     rdx, aName_2; "Name"
0x1800ad262  mov     rcx, rbx
0x1800ad265  call    sub_1800D0DAC
0x1800ad26a  mov     [rdi+40h], eax
0x1800ad26d  cmp     eax, r13d
0x1800ad270  jnz     short loc_1800AD28C
0x1800ad272  mov     [rsp+78h+var_58], r12
0x1800ad277  lea     r9, aName_2; "Name"
0x1800ad27e  mov     r8d, ebp
0x1800ad281  mov     edx, r14d
0x1800ad284  mov     rcx, rsi
0x1800ad287  call    sub_180098E44
0x1800ad28c  lea     rdx, aType_0; "Type"
0x1800ad293  mov     rcx, rbx
0x1800ad296  call    sub_1800D0DAC
0x1800ad29b  mov     [rdi+44h], eax
0x1800ad29e  cmp     eax, r13d
0x1800ad2a1  jnz     short loc_1800AD2BD
0x1800ad2a3  mov     [rsp+78h+var_58], r12
0x1800ad2a8  lea     r9, aType_0; "Type"
0x1800ad2af  mov     r8d, ebp
0x1800ad2b2  mov     edx, r14d
0x1800ad2b5  mov     rcx, rsi
0x1800ad2b8  call    sub_180098E44
0x1800ad2bd  lea     rdx, aDatecreate_0; "DateCreate"
0x1800ad2c4  mov     rcx, rbx
0x1800ad2c7  call    sub_1800D0DAC
  ... truncated ...
```
