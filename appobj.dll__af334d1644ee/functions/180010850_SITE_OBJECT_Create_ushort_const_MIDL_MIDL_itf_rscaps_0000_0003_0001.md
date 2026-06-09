# SITE_OBJECT::Create(ushort const *,__MIDL___MIDL_itf_rscaps_0000_0003_0001)

- ea: `0x180010850`
- end: `0x180010cb3`
- name: `?Create@SITE_OBJECT@@QEAAJPEBGW4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@@Z`
- size: `1123`
- prototype: `__int64 __fastcall(_QWORD *, const unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f234`
- `0x180010cc0`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x180005ba8`
- `0x180010850`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800109d9`
- `msvcrt!_ultow_s` at `0x1800109d9`

## string_xrefs

- `0x180010abf`: `protocol`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT::Create(_QWORD *a1, const unsigned __int8 *a2, int a3)
{
  int v6; // r15d
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  errno_t v10; // eax
  unsigned int i; // r14d
  int v12; // edi
  int v13; // edi
  const unsigned __int16 *v14; // r8
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Value; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+90h] [rbp-70h]
  __int16 v27; // [rsp+94h] [rbp-6Ch]
  int v28; // [rsp+98h] [rbp-68h]
  _BYTE v29[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v30; // [rsp+C0h] [rbp-40h]
  int v31; // [rsp+C8h] [rbp-38h]
  __int16 v32; // [rsp+CCh] [rbp-34h]
  int v33; // [rsp+D0h] [rbp-30h]
  wchar_t Buffer[64]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v35; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v36[510]; // [rsp+162h] [rbp+62h] BYREF
  __int16 v37; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v38[510]; // [rsp+362h] [rbp+262h] BYREF

  v21 = 0;
  Value = 0;
  v20 = 0;
  v16 = 0;
  v19 = 0;
  v18 = 0;
  memset_0(v36, 0, sizeof(v36));
  v27 = 256;
  v25 = (unsigned __int16 *)&v35;
  v26 = 512;
  v28 = 0;
  v35 = 0;
  v6 = 0;
  memset_0(v38, 0, sizeof(v38));
  v7 = (__int64 *)a1[23];
  v30 = (unsigned __int16 *)&v37;
  v37 = 0;
  v22 = 0;
  v23 = 0;
  v8 = *v7;
  v31 = 512;
  v32 = 256;
  v33 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(v8 + 64))(
         v7,
         L"name",
         &v21,
         0,
         0);
  if ( v9 >= 0 )
  {
    v9 = STRU::Copy((STRU *)v29, (const unsigned __int8 *)v21);
    if ( v9 >= 0 )
    {
      v9 = STRU::Copy((STRU *)(a1 + 2), (const unsigned __int8 *)v30);
      if ( v9 >= 0 )
      {
        v9 = COMMAND_OBJECT::AddAttribute((COMMAND_OBJECT *)a1, L"SITE.NAME", v21);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)a1[23]
                                                                                                  + 48LL))(
                 a1[23],
                 L"id",
                 &Value,
                 0,
                 0);
          if ( v9 >= 0 )
          {
            v10 = _ultow_s(Value, Buffer, 0x40u, 10);
            v9 = v10;
            if ( v10 > 0 )
              v9 = (unsigned __int16)v10 | 0x80070000;
            if ( v9 >= 0 )
            {
              v9 = COMMAND_OBJECT::AddAttribute((COMMAND_OBJECT *)a1, L"SITE.ID", Buffer);
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)a1[23] + 32LL))(
                       a1[23],
                       L"bindings",
                       &v20);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 40LL))(v20, &v19);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(v19, &v18);
                    if ( v9 >= 0 )
                    {
                      for ( i = 0; i < v18; ++i )
                      {
                        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 32LL))(
                               v19,
                               i,
                               &v16);
                        if ( v9 < 0 )
                          goto LABEL_38;
                        v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                               v16,
                               L"protocol",
                               &v22,
                               0,
                               0);
                        if ( v9 < 0 )
                          goto LABEL_38;
                        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                               v16,
                               L"bindingInformation",
                               &v23,
                               0,
                               0);
                        if ( v9 < 0 )
                          goto LABEL_38;
                        if ( v6 )
                        {
                          v9 = STRU::Append((STRU *)v24, (const unsigned __int8 *)L",");
                          if ( v9 < 0 )
                            goto LABEL_38;
                        }
                        v9 = STRU::Append((STRU *)v24, (const unsigned __int8 *)v22);
                        if ( v9 < 0 )
                          goto LABEL_38;
                        v9 = STRU::Append((STRU *)v24, (const unsigned __int8 *)L"/");
                        if ( v9 < 0 )
                          goto LABEL_38;
                        v9 = STRU::Append((STRU *)v24, (const unsigned __int8 *)v23);
                        if ( v9 < 0 )
                          goto LABEL_38;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                        v6 = v28;
                        v16 = 0;
                      }
                      v9 = COMMAND_OBJECT::AddAttribute((COMMAND_OBJECT *)a1, L"bindings", v25);
                      if ( v9 >= 0 )
                      {
                        if ( a3 )
                        {
                          v12 = a3 - 1;
                          if ( v12 )
                          {
                            v13 = v12 - 1;
                            if ( v13 )
                              v14 = v13 == 1 ? L"Stopped" : L"Unknown";
                            else
                              v14 = L"Stopping";
                          }
                          else
                          {
                            v14 = L"Started";
                          }
                        }
                        else
                        {
                          v14 = L"Starting";
                        }
                        v9 = COMMAND_OBJECT::AddAttribute((COMMAND_OBJECT *)a1, L"state", v14);
                        if ( v9 >= 0 )
                        {
                          if ( a2 )
                            v9 = STRU::Copy((STRU *)(a1 + 16), a2);
                          else
                            v9 = -2147024809;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_38:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v29);
  BUFFER::~BUFFER((BUFFER *)v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010850  mov     [rsp-8+arg_10], rbx
0x180010855  push    rbp
0x180010856  push    rsi
0x180010857  push    rdi
0x180010858  push    r12
0x18001085a  push    r13
0x18001085c  push    r14
0x18001085e  push    r15
0x180010860  lea     rbp, [rsp-470h]
0x180010868  sub     rsp, 570h
0x18001086f  mov     rax, cs:__security_cookie
0x180010876  xor     rax, rsp
0x180010879  mov     [rbp+4A0h+var_40], rax
0x180010880  xor     r13d, r13d
0x180010883  mov     edi, r8d
0x180010886  mov     r12, rdx
0x180010889  mov     [rsp+5A0h+var_550], r13
0x18001088e  mov     rsi, rcx
0x180010891  mov     [rsp+5A0h+Value], r13d
0x180010896  mov     r14d, 1FEh
0x18001089c  mov     [rsp+5A0h+var_558], r13
0x1800108a1  mov     r8d, r14d; Size
0x1800108a4  mov     [rsp+5A0h+var_570], r13
0x1800108a9  xor     edx, edx; Val
0x1800108ab  mov     [rsp+5A0h+var_560], r13
0x1800108b0  lea     rcx, [rbp+4A0h+var_43E]; void *
0x1800108b4  mov     [rsp+5A0h+var_564], r13d
0x1800108b9  call    memset_0
0x1800108be  lea     rax, [rbp+4A0h+var_440]
0x1800108c2  mov     [rbp+4A0h+var_50C], 100h
0x1800108c8  lea     ebx, [r14+2]
0x1800108cc  mov     [rbp+4A0h+var_518], rax
0x1800108d0  mov     r8d, r14d; Size
0x1800108d3  mov     [rbp+4A0h+var_510], ebx
0x1800108d6  xor     edx, edx; Val
0x1800108d8  mov     [rbp+4A0h+var_508], r13d
0x1800108dc  lea     rcx, [rbp+4A0h+var_23E]; void *
0x1800108e3  mov     [rbp+4A0h+var_440], r13w
0x1800108e8  mov     r15d, r13d
0x1800108eb  call    memset_0
0x1800108f0  mov     rcx, [rsi+0B8h]
0x1800108f7  lea     rax, [rbp+4A0h+var_240]
0x1800108fe  mov     [rbp+4A0h+var_4E0], rax
0x180010902  lea     r8, [rsp+5A0h+var_550]
0x180010907  mov     [rbp+4A0h+var_240], r13w
0x18001090f  lea     rdx, aName_0; "name"
0x180010916  mov     [rsp+5A0h+var_548], r13
0x18001091b  xor     r9d, r9d
0x18001091e  mov     [rsp+5A0h+var_540], r13
0x180010923  mov     rax, [rcx]
0x180010926  mov     [rbp+4A0h+var_4D8], ebx
0x180010929  mov     [rbp+4A0h+var_4D4], 100h
0x18001092f  mov     [rbp+4A0h+var_4D0], r13d
0x180010933  mov     rax, [rax+40h]
0x180010937  mov     [rsp+5A0h+var_580], r13
0x18001093c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010941  mov     ebx, eax
0x180010943  test    eax, eax
0x180010945  js      loc_180010C23
0x18001094b  mov     rdx, [rsp+5A0h+var_550]; unsigned __int16 *
0x180010950  lea     rcx, [rbp+4A0h+var_500]; this
0x180010954  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010959  mov     ebx, eax
0x18001095b  test    eax, eax
0x18001095d  js      loc_180010C23
0x180010963  mov     rdx, [rbp+4A0h+var_4E0]; unsigned __int16 *
0x180010967  lea     rcx, [rsi+10h]; this
0x18001096b  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010970  mov     ebx, eax
0x180010972  test    eax, eax
0x180010974  js      loc_180010C23
0x18001097a  mov     r8, [rsp+5A0h+var_550]; unsigned __int16 *
0x18001097f  lea     rdx, aSiteName; "SITE.NAME"
0x180010986  mov     rcx, rsi; this
0x180010989  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001098e  mov     ebx, eax
0x180010990  test    eax, eax
0x180010992  js      loc_180010C23
0x180010998  mov     rcx, [rsi+0B8h]
0x18001099f  lea     r8, [rsp+5A0h+Value]
0x1800109a4  xor     r9d, r9d
0x1800109a7  mov     [rsp+5A0h+var_580], r13
0x1800109ac  lea     rdx, aId; "id"
0x1800109b3  mov     rax, [rcx]
0x1800109b6  mov     rax, [rax+30h]
0x1800109ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109bf  mov     ebx, eax
0x1800109c1  test    eax, eax
0x1800109c3  js      loc_180010C23
0x1800109c9  mov     ecx, [rsp+5A0h+Value]; Value
0x1800109cd  lea     r9d, [r13+0Ah]; Radix
0x1800109d1  lea     r8d, [r13+40h]; BufferCount
0x1800109d5  lea     rdx, [rbp+4A0h+Buffer]; Buffer
0x1800109d9  call    cs:__imp__ultow_s
0x1800109df  mov     ebx, eax
0x1800109e1  test    eax, eax
0x1800109e3  jle     short loc_1800109EE
0x1800109e5  movzx   ebx, ax
0x1800109e8  or      ebx, 80070000h
0x1800109ee  test    ebx, ebx
0x1800109f0  js      loc_180010C23
0x1800109f6  lea     r8, [rbp+4A0h+Buffer]; unsigned __int16 *
0x1800109fa  mov     rcx, rsi; this
0x1800109fd  lea     rdx, aSiteId; "SITE.ID"
0x180010a04  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180010a09  mov     ebx, eax
0x180010a0b  test    eax, eax
0x180010a0d  js      loc_180010C23
0x180010a13  mov     rcx, [rsi+0B8h]
0x180010a1a  lea     r8, [rsp+5A0h+var_558]
0x180010a1f  lea     rdx, aBindings_0; "bindings"
0x180010a26  mov     rax, [rcx]
0x180010a29  mov     rax, [rax+20h]
0x180010a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a32  mov     ebx, eax
0x180010a34  test    eax, eax
0x180010a36  js      loc_180010C23
0x180010a3c  mov     rcx, [rsp+5A0h+var_558]
0x180010a41  lea     rdx, [rsp+5A0h+var_560]
0x180010a46  mov     rax, [rcx]
0x180010a49  mov     rax, [rax+28h]
0x180010a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a52  mov     ebx, eax
0x180010a54  test    eax, eax
0x180010a56  js      loc_180010C23
0x180010a5c  mov     rcx, [rsp+5A0h+var_560]
0x180010a61  lea     rdx, [rsp+5A0h+var_564]
0x180010a66  mov     rax, [rcx]
0x180010a69  mov     rax, [rax+18h]
0x180010a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a72  mov     ebx, eax
0x180010a74  test    eax, eax
0x180010a76  js      loc_180010C23
0x180010a7c  mov     r14d, r13d
0x180010a7f  cmp     r14d, [rsp+5A0h+var_564]
0x180010a84  jnb     loc_180010B9A
0x180010a8a  mov     rcx, [rsp+5A0h+var_560]
0x180010a8f  lea     r8, [rsp+5A0h+var_570]
0x180010a94  mov     edx, r14d
0x180010a97  mov     rax, [rcx]
0x180010a9a  mov     rax, [rax+20h]
0x180010a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa3  mov     ebx, eax
0x180010aa5  test    eax, eax
0x180010aa7  js      loc_180010C23
0x180010aad  mov     rcx, [rsp+5A0h+var_570]
0x180010ab2  lea     r8, [rsp+5A0h+var_548]
0x180010ab7  xor     r9d, r9d
0x180010aba  mov     [rsp+5A0h+var_580], r13
0x180010abf  lea     rdx, aProtocol; "protocol"
0x180010ac6  mov     rax, [rcx]
0x180010ac9  mov     rax, [rax+40h]
0x180010acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ad2  mov     ebx, eax
0x180010ad4  test    eax, eax
0x180010ad6  js      loc_180010C23
0x180010adc  mov     rcx, [rsp+5A0h+var_570]
0x180010ae1  lea     r8, [rsp+5A0h+var_540]
0x180010ae6  xor     r9d, r9d
0x180010ae9  mov     [rsp+5A0h+var_580], r13
0x180010aee  lea     rdx, aBindinginforma; "bindingInformation"
0x180010af5  mov     rax, [rcx]
0x180010af8  mov     rax, [rax+40h]
0x180010afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b01  mov     ebx, eax
0x180010b03  test    eax, eax
0x180010b05  js      loc_180010C23
0x180010b0b  test    r15d, r15d
0x180010b0e  jz      short loc_180010B2B
0x180010b10  lea     rdx, asc_18003991C; ","
0x180010b17  lea     rcx, [rsp+5A0h+var_538]; this
0x180010b1c  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b21  mov     ebx, eax
0x180010b23  test    eax, eax
0x180010b25  js      loc_180010C23
0x180010b2b  mov     rdx, [rsp+5A0h+var_548]; unsigned __int16 *
0x180010b30  lea     rcx, [rsp+5A0h+var_538]; this
0x180010b35  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b3a  mov     ebx, eax
0x180010b3c  test    eax, eax
0x180010b3e  js      loc_180010C23
0x180010b44  lea     rdx, SubStr; "/"
0x180010b4b  lea     rcx, [rsp+5A0h+var_538]; this
0x180010b50  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b55  mov     ebx, eax
0x180010b57  test    eax, eax
0x180010b59  js      loc_180010C23
0x180010b5f  mov     rdx, [rsp+5A0h+var_540]; unsigned __int16 *
0x180010b64  lea     rcx, [rsp+5A0h+var_538]; this
0x180010b69  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b6e  mov     ebx, eax
0x180010b70  test    eax, eax
0x180010b72  js      loc_180010C23
0x180010b78  mov     rcx, [rsp+5A0h+var_570]
0x180010b7d  mov     rax, [rcx]
0x180010b80  mov     rax, [rax+10h]
0x180010b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b89  mov     r15d, [rbp+4A0h+var_508]
0x180010b8d  inc     r14d
0x180010b90  mov     [rsp+5A0h+var_570], r13
0x180010b95  jmp     loc_180010A7F
0x180010b9a  mov     r8, [rbp+4A0h+var_518]; unsigned __int16 *
0x180010b9e  lea     rdx, aBindings_0; "bindings"
0x180010ba5  mov     rcx, rsi; this
0x180010ba8  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180010bad  mov     ebx, eax
0x180010baf  test    eax, eax
0x180010bb1  js      short loc_180010C23
0x180010bb3  test    edi, edi
0x180010bb5  jz      short loc_180010BEA
0x180010bb7  sub     edi, 1
0x180010bba  jz      short loc_180010BE1
0x180010bbc  sub     edi, 1
0x180010bbf  jz      short loc_180010BD8
0x180010bc1  cmp     edi, 1
0x180010bc4  jz      short loc_180010BCF
0x180010bc6  lea     r8, aUnknown_0; "Unknown"
0x180010bcd  jmp     short loc_180010BF1
0x180010bcf  lea     r8, aStopped; "Stopped"
0x180010bd6  jmp     short loc_180010BF1
0x180010bd8  lea     r8, aStopping; "Stopping"
0x180010bdf  jmp     short loc_180010BF1
0x180010be1  lea     r8, aStarted; "Started"
0x180010be8  jmp     short loc_180010BF1
0x180010bea  lea     r8, aStarting; "Starting"
0x180010bf1  lea     rdx, aState; "state"
0x180010bf8  mov     rcx, rsi; this
0x180010bfb  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180010c00  mov     ebx, eax
0x180010c02  test    eax, eax
0x180010c04  js      short loc_180010C23
0x180010c06  test    r12, r12
0x180010c09  jnz     short loc_180010C12
0x180010c0b  mov     ebx, 80070057h
0x180010c10  jmp     short loc_180010C23
0x180010c12  lea     rcx, [rsi+80h]; this
0x180010c19  mov     rdx, r12; unsigned __int16 *
0x180010c1c  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010c21  mov     ebx, eax
0x180010c23  mov     rcx, [rsp+5A0h+var_558]
0x180010c28  test    rcx, rcx
0x180010c2b  jz      short loc_180010C3E
0x180010c2d  mov     rax, [rcx]
0x180010c30  mov     rax, [rax+10h]
0x180010c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c39  mov     [rsp+5A0h+var_558], r13
0x180010c3e  mov     rcx, [rsp+5A0h+var_570]
0x180010c43  test    rcx, rcx
0x180010c46  jz      short loc_180010C59
0x180010c48  mov     rax, [rcx]
0x180010c4b  mov     rax, [rax+10h]
0x180010c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c54  mov     [rsp+5A0h+var_570], r13
0x180010c59  mov     rcx, [rsp+5A0h+var_560]
0x180010c5e  test    rcx, rcx
0x180010c61  jz      short loc_180010C74
0x180010c63  mov     rax, [rcx]
0x180010c66  mov     rax, [rax+10h]
0x180010c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c6f  mov     [rsp+5A0h+var_560], r13
0x180010c74  lea     rcx, [rbp+4A0h+var_500]; this
0x180010c78  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010c7d  lea     rcx, [rsp+5A0h+var_538]; this
0x180010c82  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010c87  mov     eax, ebx
0x180010c89  mov     rcx, [rbp+4A0h+var_40]
0x180010c90  xor     rcx, rsp; StackCookie
0x180010c93  call    __security_check_cookie
0x180010c98  mov     rbx, [rsp+5A0h+arg_10]
0x180010ca0  add     rsp, 570h
0x180010ca7  pop     r15
0x180010ca9  pop     r14
0x180010cab  pop     r13
0x180010cad  pop     r12
0x180010caf  pop     rdi
0x180010cb0  pop     rsi
0x180010cb1  pop     rbp
0x180010cb2  retn
```
