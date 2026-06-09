# sub_140CBDCD0

- ea: `0x140cbdcd0`
- end: `0x140cbe557`
- name: `sub_140CBDCD0`
- size: `2183`
- prototype: ``
- caller_count: `8`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140364890`
- `0x1404ee5c0`
- `0x140d95450`
- `0x1411aef00`
- `0x141294b90`
- `0x14139c6f0`
- `0x141efa9a0`
- `0x14247c850`

## callees

- `0x1400597c4`
- `0x1400aa000`
- `0x1400d5e40`
- `0x140108d10`
- `0x140192990`
- `0x140214bb0`
- `0x1402eb200`
- `0x1405408b0`
- `0x1408d2b60`
- `0x1408d2bb0`
- `0x1408d6570`
- `0x140cbdcd0`
- `0x140e23370`
- `0x140f3cca0`
- `0x14131fd60`
- `0x1413f4a70`

## import_xrefs

- `KERNEL32!Sleep` at `0x140cbe0f1`
- `KERNEL32!Sleep` at `0x140cbe0f1`
- `KERNEL32!GetLastError` at `0x140cbe176`
- `KERNEL32!GetLastError` at `0x140cbe176`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140cbe0e6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140cbe271`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140cbe4c0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140cbe0e6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140cbe271`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140cbe4c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140cbe145`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140cbe260`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140cbe4b5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140cbe145`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140cbe260`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140cbe4b5`
- `ole32!OleSetClipboard` at `0x140cbddc0`
- `ole32!OleSetClipboard` at `0x140cbe025`
- `ole32!OleSetClipboard` at `0x140cbe0f9`
- `ole32!OleSetClipboard` at `0x140cbddc0`
- `ole32!OleSetClipboard` at `0x140cbe025`
- `ole32!OleSetClipboard` at `0x140cbe0f9`
- `USER32!EmptyClipboard` at `0x140cbe168`
- `USER32!EmptyClipboard` at `0x140cbe168`
- `USER32!CloseClipboard` at `0x140cbdd98`
- `USER32!CloseClipboard` at `0x140cbe3ef`
- `USER32!CloseClipboard` at `0x140cbdd98`
- `USER32!CloseClipboard` at `0x140cbe3ef`
- `USER32!SetClipboardData` at `0x140cbe334`
- `USER32!SetClipboardData` at `0x140cbe359`
- `USER32!SetClipboardData` at `0x140cbe367`
- `USER32!SetClipboardData` at `0x140cbe375`
- `USER32!SetClipboardData` at `0x140cbe383`
- `USER32!SetClipboardData` at `0x140cbe3a3`
- `USER32!SetClipboardData` at `0x140cbe3e0`
- `USER32!SetClipboardData` at `0x140cbe334`
- `USER32!SetClipboardData` at `0x140cbe359`
- `USER32!SetClipboardData` at `0x140cbe367`
- `USER32!SetClipboardData` at `0x140cbe375`
- `USER32!SetClipboardData` at `0x140cbe383`
- `USER32!SetClipboardData` at `0x140cbe3a3`
- `USER32!SetClipboardData` at `0x140cbe3e0`
- `USER32!OpenClipboard` at `0x140cbdf71`
- `USER32!OpenClipboard` at `0x140cbdfc0`
- `USER32!OpenClipboard` at `0x140cbe153`
- `USER32!OpenClipboard` at `0x140cbdf71`
- `USER32!OpenClipboard` at `0x140cbdfc0`
- `USER32!OpenClipboard` at `0x140cbe153`
- `GDI32!CreatePalette` at `0x140cbe3cf`
- `GDI32!CreatePalette` at `0x140cbe3cf`
- `Mso20Win32Client!__imp_Mso20Win32Client_7228` at `0x140cbdee3`
- `Mso20Win32Client!__imp_Mso20Win32Client_7228` at `0x140cbdee3`
- `Mso20Win32Client!Mso20Win32Client_16175` at `0x140cbe1c6`
- `Mso20Win32Client!Mso20Win32Client_16175` at `0x140cbe1c6`
- `Mso20Win32Client!Mso20Win32Client_17625` at `0x140cbe217`
- `Mso20Win32Client!Mso20Win32Client_17625` at `0x140cbe217`
- `Mso20Win32Client!Mso20Win32Client_38572` at `0x140cbe4e5`
- `Mso20Win32Client!Mso20Win32Client_38572` at `0x140cbe4e5`
- `Mso20Win32Client!Mso20Win32Client_43741` at `0x140cbe4d0`
- `Mso20Win32Client!Mso20Win32Client_43741` at `0x140cbe4d0`

## pseudocode

```c
__int64 __fastcall sub_140CBDCD0(int a1, void *a2, int a3, int a4, int a5)
{
  int v6; // r12d
  char v7; // r14
  unsigned int v8; // r15d
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // r8
  int v22; // ebx
  HRESULT v23; // eax
  int v24; // r9d
  bool v25; // zf
  void *v26; // rcx
  __int64 v27; // rbx
  DWORD LastError; // eax
  void *v29; // rcx
  __int64 v30; // rcx
  unsigned __int8 v31; // al
  unsigned int v32; // edi
  __int64 v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rcx
  HPALETTE Palette; // rax
  void *v37; // rcx
  __int64 v38; // rax
  HWND v39; // rcx
  int v41; // [rsp+30h] [rbp-71h] BYREF
  int v42; // [rsp+34h] [rbp-6Dh]
  void ***v43; // [rsp+38h] [rbp-69h] BYREF
  char v44; // [rsp+40h] [rbp-61h] BYREF
  HANDLE hMem; // [rsp+48h] [rbp-59h] BYREF
  const char *v46; // [rsp+50h] [rbp-51h] BYREF
  _QWORD v47[3]; // [rsp+58h] [rbp-49h] BYREF
  void **v48; // [rsp+70h] [rbp-31h] BYREF
  const char *v49; // [rsp+78h] [rbp-29h]
  DWORD v50; // [rsp+80h] [rbp-21h]
  __int16 v51; // [rsp+84h] [rbp-1Dh]
  void *Block[2]; // [rsp+88h] [rbp-19h]
  __m128i si128; // [rsp+98h] [rbp-9h]
  __int16 v54; // [rsp+A8h] [rbp+7h]

  v41 = a3;
  hMem = a2;
  v42 = a1;
  v6 = -1;
  LODWORD(v43) = -1;
  v7 = 1;
  v8 = 1;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v10 = *ThreadLocalStoragePointer;
  if ( !*(_DWORD *)(*(_QWORD *)(*ThreadLocalStoragePointer + 304) + 1576LL) )
    goto LABEL_104;
  if ( a4 )
  {
    v11 = *(_QWORD *)(qword_144085E10 + 672);
    if ( v11 )
    {
      if ( (*(_BYTE *)(qword_144085E10 + 616) & 2) == 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *(_QWORD *)(qword_144085E10 + 672) = 0;
        a3 = v41;
      }
    }
  }
  if ( !a5 )
  {
LABEL_104:
    if ( !a3 || a4 || OpenClipboard(hWndNewOwner) )
    {
      dword_144185218 = 1;
      if ( !a4 )
      {
        v27 = 0;
        goto LABEL_62;
      }
      v22 = 10;
      if ( !(unsigned int)sub_1400AA000(50884814) )
      {
        v43 = (void ***)"FSetClipData: FEnsureWinOleInited failed";
        sub_140192990(7997193, 181, 50, 2, (__int64)&v43);
        goto LABEL_59;
      }
      v23 = OleSetClipboard(0);
      if ( v23 )
      {
        while ( 1 )
        {
          v25 = --v22 == 0;
          if ( v22 <= 0 )
            break;
          v49 = "HR";
          v50 = v23;
          *(_OWORD *)Block = 0;
          si128.m128i_i64[0] = 0;
          si128.m128i_i64[1] = 7;
          LOWORD(Block[0]) = 0;
          v54 = 4;
          v48 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
          v46 = "FSetClipData: OleSetClipboard failed";
          sub_1402EB200(7997194, 181, 50, v24, (__int64)&v46);
          if ( si128.m128i_i64[1] > 7uLL )
          {
            v26 = Block[0];
            if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
            {
              v26 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v26 - 8) > 0x1F )
                invoke_watson(0, 0, 0, 0, 0);
            }
            free(v26);
          }
          Sleep(0xC8u);
          v23 = OleSetClipboard(0);
          if ( !v23 )
          {
            v25 = v22 == 0;
            break;
          }
        }
        if ( v25 )
        {
          sub_1400597C4(7997195, 187, 15, 4, L"FSetClipData: OleSetClipboard failed");
          goto LABEL_59;
        }
      }
      v27 = 0;
      if ( OpenClipboard(hWndNewOwner) )
      {
        if ( !EmptyClipboard() )
        {
          LastError = GetLastError();
          v49 = "LastError";
          v50 = LastError;
          v51 = 4;
          *(_OWORD *)Block = 0;
          si128 = _mm_load_si128((const __m128i *)&xmmword_14375CD40);
          LOWORD(Block[0]) = 0;
          v48 = (void **)off_14380D168;
          if ( (unsigned __int8)Mso20Win32Client_16175(7997196, 181, 50, 2) )
          {
            v43 = &v48;
            v47[0] = &Mso::Logging::CompositeStructuredTrace::`vftable';
            v47[1] = &v43;
            v47[2] = &v44;
            Mso20Win32Client_17625(7997196, 181, 50, 2, "FSetClipData: clip not empty", v47);
          }
          if ( si128.m128i_i64[1] > 7uLL )
          {
            v29 = Block[0];
            if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
            {
              v29 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v29 - 8) > 0x1F )
                invoke_watson(0, 0, 0, 0, 0);
            }
            free(v29);
          }
          Block[0] = (void *)19937;
          si128 = _mm_load_si128((const __m128i *)&xmmword_14373C0D0);
          goto LABEL_59;
        }
        sub_140E23370();
LABEL_62:
        dword_144185218 = 0;
        if ( a5 )
        {
          v30 = *(_QWORD *)(*(_QWORD *)(v10 + 304) + 32LL);
          if ( v30 )
          {
            v31 = 0;
            if ( (*(_BYTE *)(v30 + 10) & 4) == 0 )
              v31 = *(_BYTE *)(v30 + 8);
            v32 = v31;
          }
          else
          {
            v32 = 127;
          }
          v33 = 8;
          if ( v32 != 2 )
            v33 = 38;
          do
          {
            if ( v32 != 2 || (unsigned __int64)(v27 - 4) <= 0x1A || v27 >= 34 )
            {
              v34 = dword_14387F710[v27];
              if ( (_DWORD)v34 != v42 )
                SetClipboardData(*(&dword_144004CC0 + v34), 0);
            }
            ++v27;
          }
          while ( v27 < v33 );
          v8 = 1;
          v6 = (int)v43;
          if ( v32 <= 1 )
            SetClipboardData(uFormat, 0);
          SetClipboardData(dword_144004D04, 0);
          SetClipboardData(dword_144004CEC, 0);
          SetClipboardData(dword_144004D0C, 0);
        }
        if ( v42 >= 0 )
        {
          SetClipboardData(*(&dword_144004CC0 + v42), hMem);
          if ( v42 == 9 )
          {
            v35 = *(_QWORD *)(*(_QWORD *)(v10 + 304) + 400LL);
            if ( *(_DWORD *)(v35 + 3780) )
            {
              Palette = CreatePalette(*(const LOGPALETTE **)(v35 + 3768));
              SetClipboardData(dword_144004CF4, Palette);
            }
          }
        }
        goto LABEL_83;
      }
    }
    return 0;
  }
  CloseClipboard();
  dword_144185218 = 1;
  if ( !(unsigned int)sub_1400AA000(50884812) || OleSetClipboard(0) )
  {
    sub_1400597C4(7997192, 187, 15, 4, L"FSetClipData: OleSetClipboard failed");
LABEL_59:
    v6 = 196738;
    v8 = 0;
    dword_144185218 = 0;
    sub_140E23370();
LABEL_83:
    if ( v41 )
      CloseClipboard();
    goto LABEL_85;
  }
  sub_140E23370();
  dword_144185218 = 0;
  v14 = *(_QWORD *)(v10 + 304);
  v15 = *(_QWORD *)(v14 + 32);
  if ( (*(_BYTE *)(v15 + 10) & 4) != 0 || *(_BYTE *)(v15 + 8) != 2 )
    goto LABEL_105;
  v13 = 0;
  if ( v15 )
    sub_1408D2B60(*(_QWORD *)v15, 73632, 0);
  else
    v15 = 0;
  if ( (*(_WORD *)(v15 + 424) & 0x400) != 0 )
  {
    v16 = *(_QWORD *)(*(_QWORD *)(v14 + 48) + 13280LL);
    v17 = sub_140F3CCA0(0, v16, 1, 0, *(_QWORD *)(v16 + 56));
    v18 = *(_QWORD *)(v16 + 56);
  }
  else
  {
LABEL_105:
    if ( qword_1440483A0 || !(unsigned int)sub_140108D10(v13, v12) )
    {
      v17 = sub_140F3CCA0((unsigned int)&xmmword_144182FD0 + 4, 0, 0, 0, *(_QWORD *)(*(_QWORD *)(v10 + 304) + 32LL));
      v18 = *(_QWORD *)(qword_1440483A0 + 24);
    }
    else
    {
      v19 = *(_QWORD *)(*(_QWORD *)(v10 + 304) + 32LL);
      v20 = sub_1405408B0(0);
      v17 = sub_140F3CCA0(0, v20, 1, 0, v19);
      v18 = *(_QWORD *)(*(_QWORD *)(v10 + 304) + 32LL);
    }
  }
  if ( !v17 )
  {
    v8 = 0;
LABEL_28:
    if ( !v41 )
      OpenClipboard(hWndNewOwner);
    return v8;
  }
  dword_144185218 = 1;
  if ( !v18 )
    Mso20Win32Client_7228(17363484);
  if ( (unsigned int)sub_1400AA000(50884813) && !(unsigned int)sub_1413F4A70(v17) )
  {
    dword_144185218 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    goto LABEL_28;
  }
  LOBYTE(v21) = 1;
  v6 = (unsigned __int8)sub_140214BB0(*(_QWORD *)(*(_QWORD *)(v10 + 304) + 40LL), 8, v21) != 0 ? 196737 : -1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  dword_144185218 = 0;
LABEL_85:
  if ( v6 != -1 )
  {
    v48 = &Mso::Diagnostics::ClassifiedStructuredObject<int>::`vftable';
    v49 = "ids";
    v50 = v6;
    v51 = 4;
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14375CD40);
    LOWORD(Block[0]) = 0;
    hMem = "FSetClipData";
    sub_1400D5E40(7997197, 181, 50, 2, (__int64)&hMem);
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v37 = Block[0];
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v37 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v37 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      free(v37);
    }
    v41 = 0;
    if ( !(unsigned int)Mso20Win32Client_43741(&off_143B9F470)
      || !(unsigned int)Mso20Win32Client_38572(&off_143B9F470, &v41)
      || !v41 )
    {
      v7 = 0;
    }
    if ( v42 != -1 )
    {
      v38 = *(_QWORD *)(v10 + 304);
      if ( !*(_DWORD *)(v38 + 1752) && !v7 )
      {
        v39 = qword_1440870C8;
        if ( *(_DWORD *)(v38 + 2308) )
          v39 = (HWND)xmmword_1440870D0;
        sub_14131FD60(v39);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140cbdcd0  mov     [rsp-8+arg_10], rbx
0x140cbdcd5  push    rbp
0x140cbdcd6  push    rsi
0x140cbdcd7  push    rdi
0x140cbdcd8  push    r12
0x140cbdcda  push    r13
0x140cbdcdc  push    r14
0x140cbdcde  push    r15
0x140cbdce0  lea     rbp, [rsp-1Fh]
0x140cbdce5  sub     rsp, 0C0h
0x140cbdcec  mov     rax, cs:__security_cookie
0x140cbdcf3  xor     rax, rsp
0x140cbdcf6  mov     [rbp+4Fh+var_40], rax
0x140cbdcfa  mov     ebx, r9d
0x140cbdd06  mov     [rbp+4Fh+var_C0], r8d
0x140cbdd0a  mov     [rbp+4Fh+hMem], rdx
0x140cbdd0e  mov     [rbp+4Fh+var_BC], ecx
0x140cbdd11  or      r12d, 0FFFFFFFFh
0x140cbdd15  mov     dword ptr [rbp+4Fh+var_B8], r12d
0x140cbdd19  lea     r14d, [r12+2]
0x140cbdd1e  mov     r15d, r14d
0x140cbdd21  mov     rax, gs:58h
0x140cbdd2a  mov     r13, [rax]
0x140cbdd2d  mov     eax, 130h
0x140cbdd32  mov     rax, [rax+r13]
0x140cbdd36  lea     esi, [r12+5]
0x140cbdd3b  mov     edi, [rbp+4Fh+arg_20]
0x140cbdd3e  xor     edx, edx
0x140cbdd40  cmp     [rax+628h], edx
0x140cbdd46  jz      loc_140CBDFAA
0x140cbdd4c  test    ebx, ebx
0x140cbdd4e  jz      short loc_140CBDD90
0x140cbdd50  mov     rax, qword_144085E10
0x140cbdd59  mov     rcx, [rax+2A0h]
0x140cbdd60  test    rcx, rcx
0x140cbdd63  jz      short loc_140CBDD90
0x140cbdd65  test    byte ptr [rax+268h], 2
0x140cbdd6c  jnz     short loc_140CBDD90
0x140cbdd6e  mov     rax, [rcx]
0x140cbdd72  mov     rax, [rax+10h]
0x140cbdd76  call    cs:__guard_dispatch_icall_fptr
0x140cbdd7c  mov     rax, cs:qword_144085E10
0x140cbdd83  xor     edx, edx
0x140cbdd85  mov     [rax+2A0h], rdx
0x140cbdd8c  mov     r8d, [rbp+4Fh+var_C0]
0x140cbdd90  test    edi, edi
0x140cbdd92  jz      loc_140CBDFAA
0x140cbdd98  call    cs:CloseClipboard
0x140cbdd9e  mov     cs:dword_144185218, r14d
0x140cbdda5  mov     ecx, 30870CCh
0x140cbddaa  call    sub_1400AA000
0x140cbddaf  xor     ebx, ebx
0x140cbddb1  test    eax, eax
0x140cbddb3  jz      loc_140CBDF7C
0x140cbddb9  xor     ecx, ecx; pDataObj
0x140cbddc0  call    cs:OleSetClipboard
0x140cbddc6  test    eax, eax
0x140cbddc8  jnz     loc_140CBDF7C
0x140cbddce  call    sub_140E23370
0x140cbddd3  mov     cs:dword_144185218, ebx
0x140cbddd9  mov     r12d, 130h
0x140cbdddf  mov     rdi, [r12+r13]
0x140cbdde3  mov     rbx, [rdi+20h]
0x140cbdde7  test    [rbx+0Ah], sil
0x140cbddeb  jnz     short loc_140CBDE50
0x140cbdded  cmp     byte ptr [rbx+8], 2
0x140cbddf1  jnz     short loc_140CBDE50
0x140cbddf3  xor     ecx, ecx
0x140cbddf5  test    rbx, rbx
0x140cbddf8  jnz     short loc_140CBDDFE
0x140cbddfa  mov     ebx, ecx
0x140cbddfc  jmp     short loc_140CBDE0E
0x140cbddfe  xor     r8d, r8d
0x140cbde01  mov     edx, 11FA0h
0x140cbde06  mov     rcx, [rbx]
0x140cbde09  call    sub_1408D2B60
0x140cbde0e  mov     eax, 400h
0x140cbde13  test    [rbx+1A8h], ax
0x140cbde1a  jz      short loc_140CBDE50
0x140cbde1c  mov     rax, [rdi+30h]
0x140cbde25  mov     rbx, [rax+33E0h]
0x140cbde2c  mov     rax, [rbx+38h]
0x140cbde30  mov     [rsp+0F0h+Reserved], rax
0x140cbde35  xor     r9d, r9d
0x140cbde38  mov     r8d, r14d
0x140cbde3b  mov     rdx, rbx
0x140cbde3e  xor     ecx, ecx
0x140cbde40  call    sub_140F3CCA0
0x140cbde45  mov     rdi, rax
0x140cbde48  mov     rax, [rbx+38h]
0x140cbde4c  xor     ebx, ebx
0x140cbde4e  jmp     short loc_140CBDEC9
0x140cbde50  xor     ebx, ebx
0x140cbde52  cmp     cs:qword_1440483A0, rbx
0x140cbde59  jnz     short loc_140CBDE9A
0x140cbde5b  nop     dword ptr [rax+rax+00h]
0x140cbde60  call    sub_140108D10
0x140cbde65  test    eax, eax
0x140cbde67  jz      short loc_140CBDE9A
0x140cbde69  mov     rax, [r12+r13]
0x140cbde6d  mov     rbx, [rax+20h]
0x140cbde71  xor     ecx, ecx
0x140cbde73  call    sub_1405408B0
0x140cbde78  mov     [rsp+0F0h+Reserved], rbx
0x140cbde7d  xor     r9d, r9d
0x140cbde80  mov     r8d, r14d
0x140cbde83  mov     rdx, rax
0x140cbde86  xor     ecx, ecx
0x140cbde88  call    sub_140F3CCA0
0x140cbde8d  mov     rdi, rax
0x140cbde90  mov     rax, [r12+r13]
0x140cbde94  mov     rax, [rax+20h]
0x140cbde98  jmp     short loc_140CBDE4C
0x140cbde9a  mov     rax, [r12+r13]
0x140cbde9e  mov     rcx, [rax+20h]
0x140cbdea2  mov     [rsp+0F0h+Reserved], rcx
0x140cbdea7  xor     r9d, r9d
0x140cbdeaa  xor     r8d, r8d
0x140cbdead  xor     edx, edx
0x140cbdeaf  lea     rcx, xmmword_144182FD0+4
0x140cbdeb6  call    sub_140F3CCA0
0x140cbdebb  mov     rdi, rax
0x140cbdebe  mov     rax, cs:qword_1440483A0
0x140cbdec5  mov     rax, [rax+18h]
0x140cbdec9  test    rdi, rdi
0x140cbdecc  jz      loc_140CBDF5E
0x140cbded2  mov     cs:dword_144185218, r14d
0x140cbded9  test    rax, rax
0x140cbdedc  jnz     short loc_140CBDEE9
0x140cbdede  mov     ecx, 108F21Ch
0x140cbdee3  call    cs:__imp_Mso20Win32Client_7228
0x140cbdee9  mov     ecx, 30870CDh
0x140cbdeee  call    sub_1400AA000
0x140cbdef3  test    eax, eax
0x140cbdef5  jz      short loc_140CBDF1D
0x140cbdef7  mov     rcx, rdi
0x140cbdefa  call    sub_1413F4A70
0x140cbdeff  nop
0x140cbdf00  test    eax, eax
0x140cbdf02  jnz     short loc_140CBDF1D
0x140cbdf04  mov     cs:dword_144185218, ebx
0x140cbdf0a  mov     rax, [rdi]
0x140cbdf0e  mov     rcx, rdi
0x140cbdf11  mov     rax, [rax+10h]
0x140cbdf15  call    cs:__guard_dispatch_icall_fptr
0x140cbdf1b  jmp     short loc_140CBDF61
0x140cbdf1d  mov     rcx, [r12+r13]
0x140cbdf21  xor     r9d, r9d
0x140cbdf24  mov     r8b, r14b
0x140cbdf27  lea     edx, [r9+8]
0x140cbdf2b  mov     rcx, [rcx+28h]
0x140cbdf2f  call    sub_140214BB0
0x140cbdf34  neg     al
0x140cbdf36  sbb     r12d, r12d
0x140cbdf39  and     r12d, 30082h
0x140cbdf40  dec     r12d
0x140cbdf43  mov     rax, [rdi]
0x140cbdf46  mov     rcx, rdi
0x140cbdf49  mov     rax, [rax+10h]
0x140cbdf4d  call    cs:__guard_dispatch_icall_fptr
0x140cbdf53  mov     cs:dword_144185218, ebx
0x140cbdf59  jmp     loc_140CBE3F5
0x140cbdf5e  mov     r15d, ebx
0x140cbdf61  cmp     [rbp+4Fh+var_C0], ebx
0x140cbdf64  jnz     loc_140CBE52D
0x140cbdf6a  mov     rcx, cs:hWndNewOwner; hWndNewOwner
0x140cbdf71  call    cs:OpenClipboard
0x140cbdf77  jmp     loc_140CBE52D
0x140cbdf7c  lea     rax, aFsetclipdataOl; "FSetClipData: OleSetClipboard failed"
0x140cbdf88  mov     [rsp+0F0h+Reserved], rax
0x140cbdf8d  mov     r9d, esi
0x140cbdf90  mov     edx, 0BBh
0x140cbdf95  mov     ecx, 7A0708h
0x140cbdf9a  mov     r8d, 0Fh
0x140cbdfa0  call    sub_1400597C4
0x140cbdfa5  jmp     loc_140CBE28C
0x140cbdfaa  test    r8d, r8d
0x140cbdfad  jz      short loc_140CBDFCE
0x140cbdfaf  test    ebx, ebx
0x140cbdfb1  jnz     short loc_140CBDFCE
0x140cbdfb3  mov     rcx, hWndNewOwner; hWndNewOwner
0x140cbdfc0  call    cs:OpenClipboard
0x140cbdfc6  test    eax, eax
0x140cbdfc8  jz      loc_140CBE267
0x140cbdfce  mov     cs:dword_144185218, r14d
0x140cbdfd5  test    ebx, ebx
0x140cbdfd7  jz      loc_140CBE2B1
0x140cbdfdd  mov     ebx, 0Ah
0x140cbdfe2  mov     ecx, 30870CEh
0x140cbdfe7  call    sub_1400AA000
0x140cbdfec  xor     ecx, ecx; pDataObj
0x140cbdfee  test    eax, eax
0x140cbdff0  jnz     short loc_140CBE025
0x140cbdff2  lea     rax, aFsetclipdataFe; "FSetClipData: FEnsureWinOleInited faile"...
0x140cbdff9  mov     [rbp+4Fh+var_B8], rax
0x140cbdffd  lea     r9d, [rbx-8]
0x140cbe001  lea     rax, [rbp+4Fh+var_B8]
0x140cbe005  mov     [rsp+0F0h+Reserved], rax
0x140cbe00a  mov     edx, 0B5h
0x140cbe00f  mov     ecx, 7A0709h
0x140cbe014  lea     r8d, [rbx+28h]
0x140cbe018  call    sub_140192990
0x140cbe01d  xor     ebx, ebx
0x140cbe020  jmp     loc_140CBE28C
0x140cbe025  call    cs:OleSetClipboard
0x140cbe02b  xor     edx, edx
0x140cbe02d  test    eax, eax
0x140cbe02f  jz      loc_140CBE14C
0x140cbe035  sub     ebx, r14d
0x140cbe040  test    ebx, ebx
0x140cbe042  jle     loc_140CBE10B
0x140cbe048  lea     rcx, aHr_0; "HR"
0x140cbe04f  mov     [rbp+4Fh+var_78], rcx
0x140cbe053  mov     [rbp+4Fh+var_70], eax
0x140cbe056  xorps   xmm0, xmm0
0x140cbe059  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x140cbe05d  mov     qword ptr [rbp+4Fh+var_58], rdx
0x140cbe061  mov     qword ptr [rbp+4Fh+var_58+8], 7
0x140cbe069  mov     word ptr [rbp+4Fh+Block], dx
0x140cbe06d  mov     [rbp+4Fh+var_48], si
0x140cbe071  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x140cbe078  mov     [rbp+4Fh+var_80], rax
0x140cbe07c  lea     rax, aFsetclipdataOl_0; "FSetClipData: OleSetClipboard failed"
0x140cbe083  mov     [rbp+4Fh+var_A0], rax
0x140cbe087  lea     rax, [rbp+4Fh+var_80]
0x140cbe08b  mov     [rsp+0F0h+var_C8], rax
0x140cbe090  lea     rax, [rbp+4Fh+var_A0]
0x140cbe094  mov     [rsp+0F0h+Reserved], rax
0x140cbe099  mov     edx, 0B5h
0x140cbe09e  mov     ecx, 7A070Ah
0x140cbe0a3  mov     r8d, 32h ; '2'
0x140cbe0a9  call    sub_1402EB200
0x140cbe0ae  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x140cbe0b2  cmp     rax, 7
0x140cbe0b6  jbe     short loc_140CBE0EC
0x140cbe0b8  mov     rcx, [rbp+4Fh+Block]
0x140cbe0bc  mov     rdx, rcx
0x140cbe0bf  lea     rax, ds:2[rax*2]
0x140cbe0c7  cmp     rax, 1000h
0x140cbe0cd  jb      short loc_140CBE0E6
0x140cbe0cf  mov     rcx, [rcx-8]; Block
0x140cbe0d9  sub     rdx, rcx
0x140cbe0dc  lea     rax, [rdx-8]
0x140cbe0e0  cmp     rax, 1Fh
0x140cbe0e4  ja      short loc_140CBE136
0x140cbe0e6  call    cs:__imp_free
0x140cbe0ec  mov     ecx, 0C8h; dwMilliseconds
0x140cbe0f1  call    cs:__imp_Sleep
0x140cbe0f7  xor     ecx, ecx; pDataObj
0x140cbe0f9  call    cs:OleSetClipboard
0x140cbe0ff  xor     edx, edx
0x140cbe101  test    eax, eax
0x140cbe103  jnz     loc_140CBE035
0x140cbe109  test    ebx, ebx
0x140cbe10b  jnz     short loc_140CBE14C
0x140cbe10d  lea     rax, aFsetclipdataOl; "FSetClipData: OleSetClipboard failed"
0x140cbe114  mov     [rsp+0F0h+Reserved], rax
0x140cbe119  mov     r9d, esi
0x140cbe11c  mov     edx, 0BBh
0x140cbe121  mov     ecx, 7A070Bh
0x140cbe126  mov     r8d, 0Fh
0x140cbe12c  call    sub_1400597C4
0x140cbe131  jmp     loc_140CBE01D
0x140cbe136  xor     ecx, ecx; Expression
0x140cbe138  mov     [rsp+0F0h+Reserved], rcx; Reserved
0x140cbe13d  xor     r9d, r9d; LineNo
0x140cbe140  xor     r8d, r8d; FileName
0x140cbe143  xor     edx, edx; FunctionName
0x140cbe145  call    cs:_invoke_watson
0x140cbe14c  mov     rcx, cs:hWndNewOwner; hWndNewOwner
0x140cbe153  call    cs:OpenClipboard
0x140cbe159  xor     ebx, ebx
0x140cbe160  test    eax, eax
0x140cbe162  jz      loc_140CBE269
0x140cbe168  call    cs:EmptyClipboard
0x140cbe16e  test    eax, eax
0x140cbe170  jnz     loc_140CBE2AA
0x140cbe176  call    cs:GetLastError
0x140cbe17c  nop
0x140cbe17d  lea     rcx, aLasterror; "LastError"
0x140cbe184  mov     [rbp+4Fh+var_78], rcx
0x140cbe188  mov     [rbp+4Fh+var_70], eax
0x140cbe18b  mov     [rbp+4Fh+var_6C], si
0x140cbe18f  xorps   xmm0, xmm0
0x140cbe192  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x140cbe196  movdqa  xmm1, cs:xmmword_14375CD40
0x140cbe19e  movdqu  [rbp+4Fh+var_58], xmm1
0x140cbe1a3  mov     word ptr [rbp+4Fh+Block], bx
0x140cbe1a7  lea     rax, off_14380D168
0x140cbe1ae  mov     [rbp+4Fh+var_80], rax
0x140cbe1b2  mov     edx, 0B5h
0x140cbe1b7  mov     edi, 7A070Ch
0x140cbe1bc  lea     r9d, [rbx+2]
0x140cbe1c0  lea     r8d, [rbx+32h]
0x140cbe1c4  mov     ecx, edi
0x140cbe1c6  call    cs:Mso20Win32Client_16175
0x140cbe1cc  test    al, al
0x140cbe1ce  jz      short loc_140CBE21E
0x140cbe1d0  lea     rax, [rbp+4Fh+var_80]
0x140cbe1d4  mov     [rbp+4Fh+var_B8], rax
  ... truncated ...
```
