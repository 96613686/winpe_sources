# CTpLogger::LogExchange(wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,long,ulong,void *,ulong,IWerByteStream *,ulong,long,ulong,ulong,long,ulong,void *,ulong,ulong,wchar_t const *)

- ea: `0x18009fe7c`
- end: `0x1800a0411`
- name: `?LogExchange@CTpLogger@@QEAAJPEB_W00KKJKPEAXKPEAUIWerByteStream@@KJKKJK1KK0@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CTpLogger *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, unsigned int, int, unsigned int, void *, unsigned int, struct IWerByteStream *, unsigned int, int, unsigned int, unsigned int, int, unsigned int, void *, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c24c`

## callees

- `0x180015520`
- `0x180050db0`
- `0x1800517cc`
- `0x1800517d8`
- `0x18009fe7c`
- `0x1800a9fb0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a0211`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a0211`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a01f5`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a03b7`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a01f5`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a03b7`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18009ff68`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0013`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0083`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a03d3`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18009ff68`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0013`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0083`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a03d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ff1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ff1c`

## string_xrefs

- `0x1800a01ae`: `	session-name: %ls\n	server-name: %ls\n	request-url: %ls\n	exchange-name: %ls\n	connect-time: %u\n	proxy-resolution-time: %u\n	xml-write-rc: %08X\n	xml-write-time: %u\n	send-xml-size: %u\n	send-xml-log-offset: %08X\n	send-bin-size: %u\n	send-bin-log-offset: %08X\n	send-time: %u\n	xml-parse-rc: %08X\n	xml-parse-time: %u\n	msft-root-check-time: %u\n	net-result-rc: %08X\n	receive-http-code: %u\n	receive-size: %u\n	receive-time: %u\n	receive-log-offset: %08X\n	headers: %ls\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTpLogger::LogExchange(
        CTpLogger *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        void *a9,
        unsigned int a10,
        struct IWerByteStream *a11,
        unsigned int a12,
        int a13,
        unsigned int a14,
        unsigned int a15,
        int a16,
        unsigned int a17,
        void *a18,
        unsigned int a19,
        unsigned int a20,
        const wchar_t *a21)
{
  unsigned int v23; // edx
  int *v24; // rsi
  unsigned int v25; // ebx
  int v26; // r13d
  unsigned int v27; // eax
  int v28; // r13d
  FILE *v29; // rcx
  const wchar_t *v30; // r8
  const wchar_t *v31; // rax
  const wchar_t *v32; // rcx
  int v33; // r13d
  FILE *v34; // rcx
  int v35; // eax
  int v36; // eax
  unsigned int v37; // r9d
  int v38; // [rsp+B0h] [rbp-90h]
  unsigned int v39; // [rsp+C0h] [rbp-80h] BYREF
  int v40; // [rsp+C4h] [rbp-7Ch]
  unsigned int v41; // [rsp+C8h] [rbp-78h]
  int v42; // [rsp+CCh] [rbp-74h]
  int v43; // [rsp+D0h] [rbp-70h]
  int v44; // [rsp+D4h] [rbp-6Ch]
  __int64 v45; // [rsp+D8h] [rbp-68h] BYREF
  void *v46; // [rsp+E0h] [rbp-60h]
  const wchar_t *v47; // [rsp+E8h] [rbp-58h]
  const wchar_t *v48; // [rsp+F0h] [rbp-50h]
  const wchar_t *v49; // [rsp+F8h] [rbp-48h]
  const wchar_t *v50; // [rsp+100h] [rbp-40h]
  char *v51; // [rsp+108h] [rbp-38h] BYREF
  char v52; // [rsp+110h] [rbp-30h]
  _OWORD v53[5]; // [rsp+120h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+170h] [rbp+30h] BYREF
  __int128 v55; // [rsp+180h] [rbp+40h]
  __int128 v56; // [rsp+190h] [rbp+50h]
  __int128 v57; // [rsp+1A0h] [rbp+60h]
  __int128 v58; // [rsp+1B0h] [rbp+70h]
  _BYTE v59[4096]; // [rsp+1C0h] [rbp+80h] BYREF

  v48 = a4;
  v49 = a3;
  v50 = a2;
  v47 = a21;
  v46 = a18;
  memset_0(&Buffer, 0, 0x50u);
  if ( !*((_DWORD *)this + 31) )
    return 1;
  v44 = -1;
  v43 = -1;
  v40 = 0;
  v42 = -1;
  v51 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v52 = 1;
  v23 = *((_DWORD *)this + 28);
  v41 = v23;
  *((_DWORD *)this + 28) = v23 + 1;
  if ( !*((_QWORD *)this + 13) )
    goto LABEL_21;
  v24 = (int *)((char *)this + 116);
  if ( !a10 )
  {
LABEL_8:
    if ( *((_DWORD *)this + 32) )
    {
      if ( a11 )
      {
        v39 = 0;
        v45 = 0;
        if ( (*(int (__fastcall **)(struct IWerByteStream *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a11 + 16LL))(
               a11,
               0,
               0,
               &v45) >= 0 )
        {
          v24 = (int *)((char *)this + 116);
          v43 = *((_DWORD *)this + 29);
          v26 = 0;
          v40 = 0;
          if ( (**(int (__fastcall ***)(struct IWerByteStream *, _BYTE *, __int64, unsigned int *, _QWORD))a11)(
                 a11,
                 v59,
                 4096,
                 &v39,
                 0) >= 0 )
          {
            do
            {
              if ( !v39 )
                break;
              if ( (unsigned int)_o_fwrite(v59, v39, 1) != 1 )
                break;
              v27 = v39;
              *v24 += v39;
              v26 += v27;
            }
            while ( (**(int (__fastcall ***)(struct IWerByteStream *, _BYTE *, __int64, unsigned int *, _QWORD))a11)(
                      a11,
                      v59,
                      4096,
                      &v39,
                      0) >= 0 );
            v40 = v26;
          }
          (*(void (__fastcall **)(struct IWerByteStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a11 + 16LL))(
            a11,
            (unsigned int)v45,
            0,
            0);
        }
      }
    }
    if ( a19 )
    {
      v28 = *v24;
      if ( (unsigned int)_o_fwrite(v46, a19, 1) != 1 )
        goto LABEL_6;
      *v24 += a19;
      v23 = v41;
LABEL_22:
      v29 = (FILE *)*((_QWORD *)this + 12);
      if ( v29 )
      {
        if ( fwprintf(v29, L"exchange %u {\n", v23) < 0 )
          goto LABEL_6;
        v30 = L"none";
        v31 = v47;
        if ( !v47 )
          v31 = L"none";
        v32 = v48;
        if ( !v48 )
          v32 = L"none";
        if ( *((_QWORD *)this + 10) )
          v30 = (const wchar_t *)*((_QWORD *)this + 10);
        v38 = v28;
        v33 = v40;
        if ( fwprintf(
               *((FILE *const *)this + 12),
               L"\tsession-name: %ls\n"
                "\tserver-name: %ls\n"
                "\trequest-url: %ls\n"
                "\texchange-name: %ls\n"
                "\tconnect-time: %u\n"
                "\tproxy-resolution-time: %u\n"
                "\txml-write-rc: %08X\n"
                "\txml-write-time: %u\n"
                "\tsend-xml-size: %u\n"
                "\tsend-xml-log-offset: %08X\n"
                "\tsend-bin-size: %u\n"
                "\tsend-bin-log-offset: %08X\n"
                "\tsend-time: %u\n"
                "\txml-parse-rc: %08X\n"
                "\txml-parse-time: %u\n"
                "\tmsft-root-check-time: %u\n"
                "\tnet-result-rc: %08X\n"
                "\treceive-http-code: %u\n"
                "\treceive-size: %u\n"
                "\treceive-time: %u\n"
                "\treceive-log-offset: %08X\n"
                "\theaders: %ls\n",
               v30,
               v50,
               v49,
               v32,
               a5,
               a6,
               a7,
               a8,
               a10,
               v44,
               v40,
               v43,
               a12,
               a13,
               a14,
               a15,
               a16,
               a17,
               a19,
               a20,
               v38,
               v31) < 0
          || fwprintf(*((FILE *const *)this + 12), L"}\n") < 0 )
        {
          goto LABEL_6;
        }
      }
      else
      {
        v33 = v40;
      }
      v34 = (FILE *)*((_QWORD *)this + 11);
      if ( v34 )
      {
        if ( fseek(v34, 0, 0) )
          goto LABEL_6;
        v35 = fread(&Buffer, 0x50u, 1u, *((FILE **)this + 11));
        if ( v35 )
        {
          if ( v35 != 1 )
            goto LABEL_6;
          v36 = Buffer;
        }
        else
        {
          memset_0(v53, 0, sizeof(v53));
          Buffer = v53[0];
          v55 = v53[1];
          v56 = v53[2];
          v57 = v53[3];
          v58 = v53[4];
          v36 = 3;
          LODWORD(Buffer) = 3;
        }
        if ( v36 == 3 )
        {
          DWORD1(Buffer) = (a5 + DWORD1(Buffer) * HIDWORD(Buffer)) / (HIDWORD(Buffer) + 1);
          DWORD2(Buffer) = (a6 + DWORD2(Buffer) * HIDWORD(Buffer)) / (HIDWORD(Buffer) + 1);
          ++HIDWORD(Buffer);
          if ( a10 )
          {
            v37 = v56 + 1;
            LODWORD(v55) = (a10 + (_DWORD)v55 * (_DWORD)v56) / ((int)v56 + 1);
            if ( a11 )
            {
              DWORD1(v55) = (v33 + DWORD1(v55) * DWORD1(v56)) / (unsigned int)(DWORD1(v56) + 1);
              ++DWORD1(v56);
            }
            DWORD2(v55) = (a12 + (_DWORD)v56 * DWORD2(v55)) / v37;
            HIDWORD(v55) = (a8 + (_DWORD)v56 * HIDWORD(v55)) / v37;
            LODWORD(v56) = v56 + 1;
          }
          if ( a19 )
          {
            DWORD2(v56) = (a19 + DWORD2(v56) * DWORD1(v57)) / (DWORD1(v57) + 1);
            HIDWORD(v56) = (a20 + DWORD1(v57) * HIDWORD(v56)) / (DWORD1(v57) + 1);
            LODWORD(v57) = (a14 + DWORD1(v57) * (_DWORD)v57) / (DWORD1(v57) + 1);
            ++DWORD1(v57);
          }
          if ( a15 != -1 )
          {
            DWORD2(v58) = (a15 + DWORD2(v58) * HIDWORD(v58)) / (HIDWORD(v58) + 1);
            ++HIDWORD(v58);
          }
          if ( a7 < 0 )
            ++DWORD2(v57);
          if ( a13 < 0 )
            ++HIDWORD(v57);
          if ( a16 < 0 )
            LODWORD(v58) = v58 + 1;
          if ( a17 - 400 <= 0xC7 )
            ++DWORD1(v58);
        }
        if ( fseek(*((FILE **)this + 11), 0, 0) || (unsigned int)_o_fwrite(&Buffer, 80, 1) != 1 )
          goto LABEL_6;
      }
      v25 = 0;
      goto LABEL_60;
    }
    v23 = v41;
LABEL_21:
    v28 = v42;
    goto LABEL_22;
  }
  v44 = *v24;
  if ( (unsigned int)_o_fwrite(a9, a10, 1) == 1 )
  {
    *v24 += a10;
    goto LABEL_8;
  }
LABEL_6:
  v25 = -2147467259;
LABEL_60:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v51);
  return v25;
}

```

## disassembly

```asm
0x18009fe7c  push    rbp
0x18009fe7e  push    rbx
0x18009fe7f  push    rsi
0x18009fe80  push    rdi
0x18009fe81  push    r12
0x18009fe83  push    r13
0x18009fe85  push    r14
0x18009fe87  push    r15
0x18009fe89  lea     rbp, [rsp-1098h]
0x18009fe91  mov     eax, 11D8h
0x18009fe96  call    _alloca_probe
0x18009fe9b  sub     rsp, rax
0x18009fe9e  mov     rax, cs:__security_cookie
0x18009fea5  xor     rax, rsp
0x18009fea8  mov     [rbp+10D0h+var_50], rax
0x18009feaf  mov     [rbp+10D0h+var_1120], r9
0x18009feb3  mov     [rbp+10D0h+var_1118], r8
0x18009feb7  mov     [rbp+10D0h+var_1110], rdx
0x18009febb  mov     rdi, rcx
0x18009febe  mov     rax, [rbp+10D0h+arg_A0]
0x18009fec5  mov     [rbp+10D0h+var_1128], rax
0x18009fec9  mov     r13, [rbp+10D0h+arg_40]
0x18009fed0  mov     r14, [rbp+10D0h+arg_50]
0x18009fed7  mov     rax, [rbp+10D0h+arg_88]
0x18009fede  mov     [rbp+10D0h+var_1130], rax
0x18009fee2  xor     edx, edx; Val
0x18009fee4  lea     r8d, [rdx+50h]; Size
0x18009fee8  lea     rcx, [rbp+10D0h+Buffer]; void *
0x18009feec  call    memset_0
0x18009fef1  cmp     dword ptr [rdi+7Ch], 0
0x18009fef5  jnz     short loc_18009FF01
0x18009fef7  mov     eax, 1
0x18009fefc  jmp     loc_1800A03EE
0x18009ff01  or      eax, 0FFFFFFFFh
0x18009ff04  mov     [rbp+10D0h+var_113C], eax
0x18009ff07  mov     [rbp+10D0h+var_1140], eax
0x18009ff0a  mov     [rbp+10D0h+var_114C], 0
0x18009ff11  mov     [rbp+10D0h+var_1144], eax
0x18009ff14  lea     rcx, [rdi+8]; lpCriticalSection
0x18009ff18  mov     [rbp+10D0h+var_1108], rcx
0x18009ff1c  call    cs:__imp_EnterCriticalSection
0x18009ff22  mov     ebx, 1
0x18009ff27  mov     [rbp+10D0h+var_1100], bl
0x18009ff2a  mov     edx, [rdi+70h]
0x18009ff2d  mov     [rbp+10D0h+var_1148], edx
0x18009ff30  lea     eax, [rdx+1]
0x18009ff33  mov     [rdi+70h], eax
0x18009ff36  mov     r9, [rdi+68h]
0x18009ff3a  mov     r15d, [rbp+10D0h+arg_90]
0x18009ff41  mov     r12d, [rbp+10D0h+arg_48]
0x18009ff48  test    r9, r9
0x18009ff4b  jz      loc_1800A009C
0x18009ff51  lea     rsi, [rdi+74h]
0x18009ff55  test    r12d, r12d
0x18009ff58  jz      short loc_18009FF7F
0x18009ff5a  mov     eax, [rsi]
0x18009ff5c  mov     [rbp+10D0h+var_113C], eax
0x18009ff5f  mov     edx, r12d
0x18009ff62  mov     r8d, ebx
0x18009ff65  mov     rcx, r13
0x18009ff68  call    cs:__imp__o_fwrite
0x18009ff6e  cmp     eax, ebx
0x18009ff70  jz      short loc_18009FF7C
0x18009ff72  mov     ebx, 80004005h
0x18009ff77  jmp     loc_1800A03E3
0x18009ff7c  add     [rsi], r12d
0x18009ff7f  cmp     dword ptr [rdi+80h], 0
0x18009ff86  jz      loc_1800A006D
0x18009ff8c  test    r14, r14
0x18009ff8f  jz      loc_1800A006D
0x18009ff95  mov     [rbp+10D0h+var_1150], 0
0x18009ff9c  mov     [rbp+10D0h+var_1138], 0
0x18009ffa4  mov     rax, [r14]
0x18009ffa7  lea     r9, [rbp+10D0h+var_1138]
0x18009ffab  xor     r8d, r8d
0x18009ffae  xor     edx, edx
0x18009ffb0  mov     rcx, r14
0x18009ffb3  mov     rax, [rax+10h]
0x18009ffb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ffbc  test    eax, eax
0x18009ffbe  js      loc_1800A006D
0x18009ffc4  lea     rsi, [rdi+74h]
0x18009ffc8  mov     eax, [rsi]
0x18009ffca  mov     [rbp+10D0h+var_1140], eax
0x18009ffcd  xor     r13d, r13d
0x18009ffd0  mov     [rbp+10D0h+var_114C], r13d
0x18009ffd4  mov     rax, [r14]
0x18009ffd7  mov     [rsp+1210h+var_11F0], r13
0x18009ffdc  lea     r9, [rbp+10D0h+var_1150]
0x18009ffe0  mov     r8d, 1000h
0x18009ffe6  lea     rdx, [rbp+10D0h+var_1050]
0x18009ffed  mov     rcx, r14
0x18009fff0  mov     rax, [rax]
0x18009fff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fff8  test    eax, eax
0x18009fffa  js      short loc_1800A0055
0x18009fffc  mov     eax, [rbp+10D0h+var_1150]
0x18009ffff  test    eax, eax
0x1800a0001  jz      short loc_1800A0051
0x1800a0003  mov     edx, eax
0x1800a0005  mov     r9, [rdi+68h]
0x1800a0009  mov     r8, rbx
0x1800a000c  lea     rcx, [rbp+10D0h+var_1050]
0x1800a0013  call    cs:__imp__o_fwrite
0x1800a0019  cmp     eax, ebx
0x1800a001b  jnz     short loc_1800A0051
0x1800a001d  mov     eax, [rbp+10D0h+var_1150]
0x1800a0020  add     [rsi], eax
0x1800a0022  add     r13d, eax
0x1800a0025  mov     rax, [r14]
0x1800a0028  mov     [rsp+1210h+var_11F0], 0
0x1800a0031  lea     r9, [rbp+10D0h+var_1150]
0x1800a0035  mov     r8d, 1000h
0x1800a003b  lea     rdx, [rbp+10D0h+var_1050]
0x1800a0042  mov     rcx, r14
0x1800a0045  mov     rax, [rax]
0x1800a0048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a004d  test    eax, eax
0x1800a004f  jns     short loc_18009FFFC
0x1800a0051  mov     [rbp+10D0h+var_114C], r13d
0x1800a0055  mov     rax, [r14]
0x1800a0058  mov     edx, dword ptr [rbp+10D0h+var_1138]
0x1800a005b  xor     r9d, r9d
0x1800a005e  xor     r8d, r8d
0x1800a0061  mov     rcx, r14
0x1800a0064  mov     rax, [rax+10h]
0x1800a0068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a006d  test    r15d, r15d
0x1800a0070  jz      short loc_1800A0099
0x1800a0072  mov     r13d, [rsi]
0x1800a0075  mov     rdx, r15
0x1800a0078  mov     r9, [rdi+68h]
0x1800a007c  mov     r8, rbx
0x1800a007f  mov     rcx, [rbp+10D0h+var_1130]
0x1800a0083  call    cs:__imp__o_fwrite
0x1800a0089  cmp     eax, ebx
0x1800a008b  jnz     loc_18009FF72
0x1800a0091  add     [rsi], r15d
0x1800a0094  mov     edx, [rbp+10D0h+var_1148]
0x1800a0097  jmp     short loc_1800A00A0
0x1800a0099  mov     edx, [rbp+10D0h+var_1148]
0x1800a009c  mov     r13d, [rbp+10D0h+var_1144]
0x1800a00a0  mov     rcx, [rdi+60h]; Stream
0x1800a00a4  mov     esi, [rbp+10D0h+arg_70]
0x1800a00aa  test    rcx, rcx
0x1800a00ad  jz      loc_1800A01DF
0x1800a00b3  mov     r8d, edx
0x1800a00b6  lea     rdx, aExchangeU; "exchange %u {\n"
0x1800a00bd  call    fwprintf
0x1800a00c2  test    eax, eax
0x1800a00c4  js      loc_18009FF72
0x1800a00ca  lea     r8, aNone; "none"
0x1800a00d1  mov     rax, [rbp+10D0h+var_1128]
0x1800a00d5  test    rax, rax
0x1800a00d8  cmovz   rax, r8
0x1800a00dc  mov     rcx, [rbp+10D0h+var_1120]
0x1800a00e0  test    rcx, rcx
0x1800a00e3  cmovz   rcx, r8
0x1800a00e7  cmp     qword ptr [rdi+50h], 0
0x1800a00ec  cmovnz  r8, [rdi+50h]
0x1800a00f1  mov     [rsp+1210h+var_1158], rax
0x1800a00f9  mov     [rsp+1210h+var_1160], r13d
0x1800a0101  mov     eax, [rbp+10D0h+arg_98]
0x1800a0107  mov     [rsp+1210h+var_1168], eax
0x1800a010e  mov     [rsp+1210h+var_1170], r15d
0x1800a0116  mov     eax, [rbp+10D0h+arg_80]
0x1800a011c  mov     [rsp+1210h+var_1178], eax
0x1800a0123  mov     eax, [rbp+10D0h+arg_78]
0x1800a0129  mov     [rsp+1210h+var_1180], eax
0x1800a0130  mov     [rsp+1210h+var_1188], esi
0x1800a0137  mov     eax, [rbp+10D0h+arg_68]
0x1800a013d  mov     [rsp+1210h+var_1190], eax
0x1800a0144  mov     eax, [rbp+10D0h+arg_60]
0x1800a014a  mov     [rsp+1210h+var_1198], eax
0x1800a014e  mov     eax, [rbp+10D0h+arg_58]
0x1800a0154  mov     [rsp+1210h+var_11A0], eax
0x1800a0158  mov     eax, [rbp+10D0h+var_1140]
0x1800a015b  mov     [rsp+1210h+var_11A8], eax
0x1800a015f  mov     r13d, [rbp+10D0h+var_114C]
0x1800a0163  mov     [rsp+1210h+var_11B0], r13d
0x1800a0168  mov     eax, [rbp+10D0h+var_113C]
0x1800a016b  mov     [rsp+1210h+var_11B8], eax
0x1800a016f  mov     [rsp+1210h+var_11C0], r12d
0x1800a0174  mov     eax, [rbp+10D0h+arg_38]
0x1800a017a  mov     [rsp+1210h+var_11C8], eax
0x1800a017e  mov     eax, [rbp+10D0h+arg_30]
0x1800a0184  mov     [rsp+1210h+var_11D0], eax
0x1800a0188  mov     eax, [rbp+10D0h+arg_28]
0x1800a018e  mov     [rsp+1210h+var_11D8], eax
0x1800a0192  mov     eax, [rbp+10D0h+arg_20]
0x1800a0198  mov     [rsp+1210h+var_11E0], eax
0x1800a019c  mov     [rsp+1210h+var_11E8], rcx
0x1800a01a1  mov     rax, [rbp+10D0h+var_1118]
0x1800a01a5  mov     [rsp+1210h+var_11F0], rax
0x1800a01aa  mov     r9, [rbp+10D0h+var_1110]
0x1800a01ae  lea     rdx, aSessionNameLsS; "\tsession-name: %ls\n\tserver-name: %ls"...
0x1800a01b5  mov     rcx, [rdi+60h]; Stream
0x1800a01b9  call    fwprintf
0x1800a01be  test    eax, eax
0x1800a01c0  js      loc_18009FF72
0x1800a01c6  lea     rdx, asc_1800C3A7C; "}\n"
0x1800a01cd  mov     rcx, [rdi+60h]; Stream
0x1800a01d1  call    fwprintf
0x1800a01d6  test    eax, eax
0x1800a01d8  jns     short loc_1800A01E3
0x1800a01da  jmp     loc_18009FF72
0x1800a01df  mov     r13d, [rbp+10D0h+var_114C]
0x1800a01e3  mov     rcx, [rdi+58h]; Stream
0x1800a01e7  test    rcx, rcx
0x1800a01ea  jz      loc_1800A03E1
0x1800a01f0  xor     r8d, r8d; Origin
0x1800a01f3  xor     edx, edx; Offset
0x1800a01f5  call    cs:__imp_fseek
0x1800a01fb  test    eax, eax
0x1800a01fd  jnz     loc_18009FF72
0x1800a0203  mov     r9, [rdi+58h]; Stream
0x1800a0207  mov     r8, rbx; ElementCount
0x1800a020a  lea     edx, [rax+50h]; ElementSize
0x1800a020d  lea     rcx, [rbp+10D0h+Buffer]; Buffer
0x1800a0211  call    cs:__imp_fread
0x1800a0217  test    eax, eax
0x1800a0219  jnz     short loc_1800A025C
0x1800a021b  xor     edx, edx; Val
0x1800a021d  lea     r8d, [rax+50h]; Size
0x1800a0221  lea     rcx, [rbp+10D0h+var_10F0]; void *
0x1800a0225  call    memset_0
0x1800a022a  movaps  xmm0, [rbp+10D0h+var_10F0]
0x1800a022e  movaps  [rbp+10D0h+Buffer], xmm0
0x1800a0232  movaps  xmm1, [rbp+10D0h+var_10E0]
0x1800a0236  movaps  [rbp+10D0h+var_1090], xmm1
0x1800a023a  movaps  xmm0, [rbp+10D0h+var_10D0]
0x1800a023e  movaps  [rbp+10D0h+var_1080], xmm0
0x1800a0242  movaps  xmm1, [rbp+10D0h+var_10C0]
0x1800a0246  movaps  [rbp+10D0h+var_1070], xmm1
0x1800a024a  movaps  xmm0, [rbp+10D0h+var_10B0]
0x1800a024e  movaps  [rbp+10D0h+var_1060], xmm0
0x1800a0252  mov     eax, 3
0x1800a0257  mov     dword ptr [rbp+10D0h+Buffer], eax
0x1800a025a  jmp     short loc_1800A0267
0x1800a025c  cmp     eax, ebx
0x1800a025e  jnz     loc_18009FF72
0x1800a0264  mov     eax, dword ptr [rbp+10D0h+Buffer]
0x1800a0267  cmp     eax, 3
0x1800a026a  jnz     loc_1800A03AE
0x1800a0270  mov     rcx, qword ptr [rbp+10D0h+Buffer+8]
0x1800a0274  shr     rcx, 20h
0x1800a0278  lea     r8d, [rcx+1]
0x1800a027c  mov     eax, ecx
0x1800a027e  imul    eax, dword ptr [rbp+10D0h+Buffer+4]
0x1800a0282  add     eax, [rbp+10D0h+arg_20]
0x1800a0288  xor     edx, edx
0x1800a028a  div     r8d
0x1800a028d  mov     dword ptr [rbp+10D0h+Buffer+4], eax
0x1800a0290  imul    ecx, dword ptr [rbp+10D0h+Buffer+8]
0x1800a0294  add     ecx, [rbp+10D0h+arg_28]
0x1800a029a  xor     edx, edx
0x1800a029c  mov     eax, ecx
0x1800a029e  div     r8d
0x1800a02a1  mov     dword ptr [rbp+10D0h+Buffer+8], eax
0x1800a02a4  mov     dword ptr [rbp+10D0h+Buffer+0Ch], r8d
0x1800a02a8  test    r12d, r12d
0x1800a02ab  jz      short loc_1800A0311
0x1800a02ad  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x1800a02b1  lea     r9d, [r8+1]
0x1800a02b5  mov     eax, r8d
0x1800a02b8  imul    eax, dword ptr [rbp+10D0h+var_1090]
0x1800a02bc  add     eax, r12d
0x1800a02bf  xor     edx, edx
0x1800a02c1  div     r9d
0x1800a02c4  mov     dword ptr [rbp+10D0h+var_1090], eax
0x1800a02c7  test    r14, r14
0x1800a02ca  jz      short loc_1800A02E3
0x1800a02cc  mov     eax, dword ptr [rbp+10D0h+var_1080+4]
0x1800a02cf  lea     ecx, [rax+1]
0x1800a02d2  imul    eax, dword ptr [rbp+10D0h+var_1090+4]
0x1800a02d6  add     eax, r13d
0x1800a02d9  xor     edx, edx
0x1800a02db  div     ecx
0x1800a02dd  mov     dword ptr [rbp+10D0h+var_1090+4], eax
0x1800a02e0  mov     dword ptr [rbp+10D0h+var_1080+4], ecx
0x1800a02e3  mov     eax, dword ptr [rbp+10D0h+var_1090+8]
0x1800a02e6  imul    eax, r8d
0x1800a02ea  add     eax, [rbp+10D0h+arg_58]
0x1800a02f0  xor     edx, edx
0x1800a02f2  div     r9d
0x1800a02f5  mov     dword ptr [rbp+10D0h+var_1090+8], eax
0x1800a02f8  mov     eax, dword ptr [rbp+10D0h+var_1090+0Ch]
0x1800a02fb  imul    eax, r8d
0x1800a02ff  add     eax, [rbp+10D0h+arg_38]
0x1800a0305  xor     edx, edx
0x1800a0307  div     r9d
0x1800a030a  mov     dword ptr [rbp+10D0h+var_1090+0Ch], eax
0x1800a030d  mov     dword ptr [rbp+10D0h+var_1080], r9d
0x1800a0311  test    r15d, r15d
0x1800a0314  jz      short loc_1800A035A
0x1800a0316  mov     ecx, dword ptr [rbp+10D0h+var_1070+4]
0x1800a0319  lea     r8d, [rcx+1]
0x1800a031d  mov     eax, ecx
0x1800a031f  imul    eax, dword ptr [rbp+10D0h+var_1080+8]
0x1800a0323  add     eax, r15d
  ... truncated ...
```
