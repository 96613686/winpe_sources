# UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)

- ea: `0x18000d910`
- end: `0x18000db35`
- name: `?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z`
- size: `549`
- prototype: `__int64 __fastcall(UndockedComponentLoadFailedEvent *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x180001098`
- `0x18000d910`
- `0x18000ed40`

## pseudocode

```c
__int64 __fastcall UndockedComponentLoadFailedEvent::FireAsimovEvent(
        UndockedComponentLoadFailedEvent *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  const WCHAR *v4; // r9
  int v5; // esi
  const WCHAR *v6; // r11
  const WCHAR *v7; // rbx
  const WCHAR *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // edx
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // rcx
  int v21; // [rsp+38h] [rbp-79h] BYREF
  int v22; // [rsp+3Ch] [rbp-75h] BYREF
  __int64 v23; // [rsp+40h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+48h] [rbp-69h] BYREF
  __int64 *v25; // [rsp+68h] [rbp-49h]
  __int64 v26; // [rsp+70h] [rbp-41h]
  const wchar_t *v27; // [rsp+78h] [rbp-39h]
  int v28; // [rsp+80h] [rbp-31h]
  int v29; // [rsp+84h] [rbp-2Dh]
  int *v30; // [rsp+88h] [rbp-29h]
  __int64 v31; // [rsp+90h] [rbp-21h]
  const WCHAR *v32; // [rsp+98h] [rbp-19h]
  int v33; // [rsp+A0h] [rbp-11h]
  int v34; // [rsp+A4h] [rbp-Dh]
  const WCHAR *v35; // [rsp+A8h] [rbp-9h]
  int v36; // [rsp+B0h] [rbp-1h]
  int v37; // [rsp+B4h] [rbp+3h]
  const WCHAR *v38; // [rsp+B8h] [rbp+7h]
  int v39; // [rsp+C0h] [rbp+Fh]
  int v40; // [rsp+C4h] [rbp+13h]
  const WCHAR *v41; // [rsp+C8h] [rbp+17h]
  int v42; // [rsp+D0h] [rbp+1Fh]
  int v43; // [rsp+D4h] [rbp+23h]
  int *v44; // [rsp+D8h] [rbp+27h]
  __int64 v45; // [rsp+E0h] [rbp+2Fh]
  const wchar_t *v46; // [rsp+E8h] [rbp+37h]
  int v47; // [rsp+F0h] [rbp+3Fh]
  int v48; // [rsp+F4h] [rbp+43h]

  if ( (unsigned int)dword_18001F140 > 5
    && (qword_18001F150 & 0x800000000000LL) != 0
    && (qword_18001F158 & 0x800000000000LL) == qword_18001F158 )
  {
    v4 = (const WCHAR *)*((_QWORD *)this + 5);
    v5 = 1;
    v6 = (const WCHAR *)*((_QWORD *)this + 4);
    v7 = (const WCHAR *)*((_QWORD *)this + 3);
    v8 = (const WCHAR *)*((_QWORD *)this + 2);
    v21 = *((_DWORD *)this + 2);
    v22 = *((_DWORD *)this + 3);
    v23 = 2164260864LL;
    v9 = -1;
    if ( a3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_BYTE *)a3 + v10) );
      v11 = v10 + 1;
    }
    else
    {
      a3 = &word_180018322;
      v11 = 1;
    }
    v47 = v11;
    v46 = a3;
    v44 = &v21;
    v12 = 2;
    v48 = 0;
    v45 = 4;
    if ( v4 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v4[v13] );
      v14 = 2 * v13 + 2;
    }
    else
    {
      v4 = &OutputString;
      v14 = 2;
    }
    v41 = v4;
    v42 = v14;
    v43 = 0;
    if ( v6 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v6[v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v6 = &OutputString;
      v16 = 2;
    }
    v38 = v6;
    v39 = v16;
    v40 = 0;
    if ( v7 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v7[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v7 = &OutputString;
      v18 = 2;
    }
    v35 = v7;
    v36 = v18;
    v37 = 0;
    if ( v8 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v8[v19] );
      v12 = 2 * v19 + 2;
    }
    else
    {
      v8 = &OutputString;
    }
    v32 = v8;
    v30 = &v22;
    v33 = v12;
    v34 = 0;
    v31 = 4;
    if ( a2 )
    {
      do
        ++v9;
      while ( *((_BYTE *)a2 + v9) );
      v5 = v9 + 1;
    }
    else
    {
      a2 = &word_180018322;
    }
    v27 = a2;
    v25 = &v23;
    v28 = v5;
    v29 = 0;
    v26 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001F140, (unsigned __int8 *)&word_18001B2A2, 0, 0, 0xBu, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d910  mov     rax, rsp
0x18000d913  mov     [rax+8], rbx
0x18000d917  mov     [rax+10h], rsi
0x18000d91b  mov     [rax+18h], rdi
0x18000d91f  mov     [rax+20h], r14
0x18000d923  push    rbp
0x18000d924  lea     rbp, [rax-5Fh]
0x18000d928  sub     rsp, 100h
0x18000d92f  mov     rax, cs:__security_cookie
0x18000d936  xor     rax, rsp
0x18000d939  mov     [rbp+57h+var_10], rax
0x18000d93d  cmp     cs:dword_18001F140, 5
0x18000d944  mov     r10, rdx
0x18000d947  jbe     loc_18000DB0A
0x18000d94d  mov     rdx, 800000000000h
0x18000d957  test    cs:qword_18001F150, rdx
0x18000d95e  jz      loc_18000DB0A
0x18000d964  mov     rax, cs:qword_18001F158
0x18000d96b  and     rax, rdx
0x18000d96e  cmp     rax, cs:qword_18001F158
0x18000d975  jnz     loc_18000DB0A
0x18000d97b  mov     eax, [rcx+8]
0x18000d97e  xor     r14d, r14d
0x18000d981  mov     r9, [rcx+28h]
0x18000d985  mov     esi, 1
0x18000d98a  mov     r11, [rcx+20h]
0x18000d98e  mov     rbx, [rcx+18h]
0x18000d992  mov     rdi, [rcx+10h]
0x18000d996  mov     [rbp+57h+var_D0], eax
0x18000d999  mov     eax, [rcx+0Ch]
0x18000d99c  mov     [rbp+57h+var_CC], eax
0x18000d99f  mov     eax, 81000000h
0x18000d9a4  mov     [rbp+57h+var_C8], rax
0x18000d9a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d9ac  test    r8, r8
0x18000d9af  jz      short loc_18000D9C1
0x18000d9b1  mov     rcx, rax
0x18000d9b4  inc     rcx
0x18000d9b7  cmp     [r8+rcx], r14b
0x18000d9bb  jnz     short loc_18000D9B4
0x18000d9bd  inc     ecx
0x18000d9bf  jmp     short loc_18000D9CA
0x18000d9c1  lea     r8, word_180018322
0x18000d9c8  mov     ecx, esi
0x18000d9ca  mov     [rbp+57h+var_18], ecx
0x18000d9cd  lea     rcx, [rbp+57h+var_D0]
0x18000d9d1  mov     [rbp+57h+var_20], r8
0x18000d9d5  lea     r8, OutputString
0x18000d9dc  mov     [rbp+57h+var_30], rcx
0x18000d9e0  mov     edx, 2
0x18000d9e5  mov     [rbp+57h+var_14], r14d
0x18000d9e9  mov     [rbp+57h+var_28], 4
0x18000d9f1  test    r9, r9
0x18000d9f4  jz      short loc_18000DA0C
0x18000d9f6  mov     rcx, rax
0x18000d9f9  inc     rcx
0x18000d9fc  cmp     [r9+rcx*2], r14w
0x18000da01  jnz     short loc_18000D9F9
0x18000da03  lea     ecx, ds:2[rcx*2]
0x18000da0a  jmp     short loc_18000DA11
0x18000da0c  mov     r9, r8
0x18000da0f  mov     ecx, edx
0x18000da11  mov     [rbp+57h+var_40], r9
0x18000da15  mov     [rbp+57h+var_38], ecx
0x18000da18  mov     [rbp+57h+var_34], r14d
0x18000da1c  test    r11, r11
0x18000da1f  jz      short loc_18000DA37
0x18000da21  mov     rcx, rax
0x18000da24  inc     rcx
0x18000da27  cmp     [r11+rcx*2], r14w
0x18000da2c  jnz     short loc_18000DA24
0x18000da2e  lea     ecx, ds:2[rcx*2]
0x18000da35  jmp     short loc_18000DA3C
0x18000da37  mov     r11, r8
0x18000da3a  mov     ecx, edx
0x18000da3c  mov     [rbp+57h+var_50], r11
0x18000da40  mov     [rbp+57h+var_48], ecx
0x18000da43  mov     [rbp+57h+var_44], r14d
0x18000da47  test    rbx, rbx
0x18000da4a  jz      short loc_18000DA62
0x18000da4c  mov     rcx, rax
0x18000da4f  inc     rcx
0x18000da52  cmp     [rbx+rcx*2], r14w
0x18000da57  jnz     short loc_18000DA4F
0x18000da59  lea     ecx, ds:2[rcx*2]
0x18000da60  jmp     short loc_18000DA67
0x18000da62  mov     rbx, r8
0x18000da65  mov     ecx, edx
0x18000da67  mov     [rbp+57h+var_60], rbx
0x18000da6b  mov     [rbp+57h+var_58], ecx
0x18000da6e  mov     [rbp+57h+var_54], r14d
0x18000da72  test    rdi, rdi
0x18000da75  jz      short loc_18000DA8D
0x18000da77  mov     rcx, rax
0x18000da7a  inc     rcx
0x18000da7d  cmp     [rdi+rcx*2], r14w
0x18000da82  jnz     short loc_18000DA7A
0x18000da84  lea     edx, ds:2[rcx*2]
0x18000da8b  jmp     short loc_18000DA90
0x18000da8d  mov     rdi, r8
0x18000da90  mov     [rbp+57h+var_70], rdi
0x18000da94  lea     rcx, [rbp+57h+var_CC]
0x18000da98  mov     [rbp+57h+var_80], rcx
0x18000da9c  mov     [rbp+57h+var_68], edx
0x18000da9f  mov     [rbp+57h+var_64], r14d
0x18000daa3  mov     [rbp+57h+var_78], 4
0x18000daab  test    r10, r10
0x18000daae  jz      short loc_18000DABE
0x18000dab0  inc     rax
0x18000dab3  cmp     [r10+rax], r14b
0x18000dab7  jnz     short loc_18000DAB0
0x18000dab9  lea     esi, [rax+1]
0x18000dabc  jmp     short loc_18000DAC5
0x18000dabe  lea     r10, word_180018322
0x18000dac5  lea     rax, [rbp+57h+var_C8]
0x18000dac9  mov     [rbp+57h+var_90], r10
0x18000dacd  mov     [rbp+57h+var_A0], rax
0x18000dad1  lea     rdx, word_18001B2A2; int
0x18000dad8  lea     rax, [rbp+57h+var_C0]
0x18000dadc  mov     [rbp+57h+var_88], esi
0x18000dadf  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x18000dae4  lea     rcx, dword_18001F140; int
0x18000daeb  xor     r9d, r9d; int
0x18000daee  mov     [rsp+100h+var_E0], 0Bh; ULONG
0x18000daf6  xor     r8d, r8d; int
0x18000daf9  mov     [rbp+57h+var_84], r14d
0x18000dafd  mov     [rbp+57h+var_98], 8
0x18000db05  call    _tlgWriteTransfer_EventWriteTransfer
0x18000db0a  xor     eax, eax
0x18000db0c  mov     rcx, [rbp+57h+var_10]
0x18000db10  xor     rcx, rsp; StackCookie
0x18000db13  call    __security_check_cookie
0x18000db18  lea     r11, [rsp+100h+var_s0]
0x18000db20  mov     rbx, [r11+10h]
0x18000db24  mov     rsi, [r11+18h]
0x18000db28  mov     rdi, [r11+20h]
0x18000db2c  mov     r14, [r11+28h]
0x18000db30  mov     rsp, r11
0x18000db33  pop     rbp
0x18000db34  retn
```
