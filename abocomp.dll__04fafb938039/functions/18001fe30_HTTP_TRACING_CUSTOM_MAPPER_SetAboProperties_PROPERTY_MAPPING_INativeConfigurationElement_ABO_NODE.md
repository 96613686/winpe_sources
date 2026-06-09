# HTTP_TRACING_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001fe30`
- end: `0x1800200d0`
- name: `?SetAboProperties@HTTP_TRACING_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `672`
- prototype: `int(HTTP_TRACING_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001fe30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020002`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001fe7b`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001fe7b`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18001ffd8`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18001ffd8`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001ff83`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001ff83`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18001ffe6`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18001ffe6`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800200ac`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800200ac`

## pseudocode

```c
__int64 __fastcall HTTP_TRACING_CUSTOM_MAPPER::SetAboProperties(
        HTTP_TRACING_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  signed int MergedConfigElement; // ebx
  unsigned int v8; // edi
  signed int LastError; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-71h] BYREF
  __int64 v14; // [rsp+40h] [rbp-69h] BYREF
  __int64 v15; // [rsp+48h] [rbp-61h] BYREF
  struct INativeConfigurationElement *v16; // [rsp+50h] [rbp-59h] BYREF
  const unsigned __int16 *v17; // [rsp+58h] [rbp-51h] BYREF
  struct _METADATA_RECORD v18; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v19[56]; // [rsp+88h] [rbp-21h] BYREF

  v16 = 0;
  v12 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v17 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v19);
  if ( a2 && a3 && a4 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/httpTracing",
                            &v16,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 32LL))(
                              v16,
                              L"traceUrls",
                              &v15);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 40LL))(v15, &v14);
        if ( MergedConfigElement >= 0 )
        {
          MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 24LL))(v14, &v13);
          if ( MergedConfigElement >= 0 )
          {
            v8 = 0;
            if ( v13 )
            {
              while ( 1 )
              {
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 32LL))(
                                        v14,
                                        v8,
                                        &v12);
                if ( MergedConfigElement < 0 )
                  break;
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
                                        v12,
                                        L"value",
                                        &v17,
                                        0,
                                        0);
                if ( MergedConfigElement < 0 )
                  break;
                if ( !MULTISZ::Append((MULTISZ *)v19, v17) )
                {
                  LastError = GetLastError();
                  MergedConfigElement = LastError;
                  if ( LastError > 0 )
                    MergedConfigElement = (unsigned __int16)LastError | 0x80070000;
                  break;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                ++v8;
                v12 = 0;
                if ( v8 >= v13 )
                  goto LABEL_13;
              }
            }
            else
            {
LABEL_13:
              v18.dwMDIdentifier = *((_DWORD *)a2 + 36);
              v18.dwMDUserType = *((_DWORD *)a2 + 37);
              v18.dwMDDataType = *((_DWORD *)a2 + 38);
              v18.dwMDAttributes = *((_DWORD *)a2 + 39);
              *(&v18.dwMDDataLen + 1) = 0;
              *(_QWORD *)&v18.dwMDDataTag = 0;
              v18.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v19);
              v18.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v19);
              MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v18, a2);
            }
          }
        }
      }
    }
  }
  else
  {
    MergedConfigElement = -2147024809;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  v10 = v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v10 = 0;
    v12 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v10 = v12;
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v16 + 16LL))(v16);
    v10 = v12;
    v16 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v12 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v19);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001fe30  push    rbp
0x18001fe32  push    rbx
0x18001fe33  push    rsi
0x18001fe34  push    rdi
0x18001fe35  push    r14
0x18001fe37  push    r15
0x18001fe39  lea     rbp, [rsp-2Fh]
0x18001fe3e  sub     rsp, 0D8h
0x18001fe45  mov     rax, cs:__security_cookie
0x18001fe4c  xor     rax, rsp
0x18001fe4f  mov     [rbp+57h+var_40], rax
0x18001fe53  xor     r15d, r15d
0x18001fe56  lea     rcx, [rbp+57h+var_78]
0x18001fe5a  mov     [rbp+57h+var_B0], r15
0x18001fe5e  mov     r14, r9
0x18001fe61  mov     [rbp+57h+var_D0], r15
0x18001fe65  mov     rbx, r8
0x18001fe68  mov     [rbp+57h+var_B8], r15
0x18001fe6c  mov     rsi, rdx
0x18001fe6f  mov     [rbp+57h+var_C0], r15
0x18001fe73  mov     [rbp+57h+var_C8], r15d
0x18001fe77  mov     [rbp+57h+var_A8], r15
0x18001fe7b  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001fe81  test    rsi, rsi
0x18001fe84  jz      loc_180020019
0x18001fe8a  test    rbx, rbx
0x18001fe8d  jz      loc_180020019
0x18001fe93  test    r14, r14
0x18001fe96  jz      loc_180020019
0x18001fe9c  mov     r9d, [rsi+0ACh]
0x18001fea3  lea     r8, [rbp+57h+var_B0]; struct INativeConfigurationElement **
0x18001fea7  and     r9d, 1; int
0x18001feab  lea     rdx, aSystemWebserve_14; "system.webServer/httpTracing"
0x18001feb2  mov     rcx, r14; this
0x18001feb5  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001feba  mov     ebx, eax
0x18001febc  test    eax, eax
0x18001febe  js      loc_18002001E
0x18001fec4  mov     rcx, [rbp+57h+var_B0]
0x18001fec8  lea     r8, [rbp+57h+var_B8]
0x18001fecc  lea     rdx, aTraceurls_0; "traceUrls"
0x18001fed3  mov     rax, [rcx]
0x18001fed6  mov     rax, [rax+20h]
0x18001feda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fedf  mov     ebx, eax
0x18001fee1  test    eax, eax
0x18001fee3  js      loc_18002001E
0x18001fee9  mov     rcx, [rbp+57h+var_B8]
0x18001feed  lea     rdx, [rbp+57h+var_C0]
0x18001fef1  mov     rax, [rcx]
0x18001fef4  mov     rax, [rax+28h]
0x18001fef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fefd  mov     ebx, eax
0x18001feff  test    eax, eax
0x18001ff01  js      loc_18002001E
0x18001ff07  mov     rcx, [rbp+57h+var_C0]
0x18001ff0b  lea     rdx, [rbp+57h+var_C8]
0x18001ff0f  mov     rax, [rcx]
0x18001ff12  mov     rax, [rax+18h]
0x18001ff16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff1b  mov     ebx, eax
0x18001ff1d  test    eax, eax
0x18001ff1f  js      loc_18002001E
0x18001ff25  mov     edi, r15d
0x18001ff28  cmp     [rbp+57h+var_C8], r15d
0x18001ff2c  jbe     short loc_18001FFA8
0x18001ff2e  mov     rcx, [rbp+57h+var_C0]
0x18001ff32  lea     r8, [rbp+57h+var_D0]
0x18001ff36  mov     edx, edi
0x18001ff38  mov     rax, [rcx]
0x18001ff3b  mov     rax, [rax+20h]
0x18001ff3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff44  mov     ebx, eax
0x18001ff46  test    eax, eax
0x18001ff48  js      loc_18002001E
0x18001ff4e  mov     rcx, [rbp+57h+var_D0]
0x18001ff52  lea     r8, [rbp+57h+var_A8]
0x18001ff56  xor     r9d, r9d
0x18001ff59  mov     [rsp+100h+var_E0], r15
0x18001ff5e  lea     rdx, aValue; "value"
0x18001ff65  mov     rax, [rcx]
0x18001ff68  mov     rax, [rax+40h]
0x18001ff6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff71  mov     ebx, eax
0x18001ff73  test    eax, eax
0x18001ff75  js      loc_18002001E
0x18001ff7b  mov     rdx, [rbp+57h+var_A8]
0x18001ff7f  lea     rcx, [rbp+57h+var_78]
0x18001ff83  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001ff89  test    eax, eax
0x18001ff8b  jz      short loc_180020002
0x18001ff8d  mov     rcx, [rbp+57h+var_D0]
0x18001ff91  mov     rax, [rcx]
0x18001ff94  mov     rax, [rax+10h]
0x18001ff98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff9d  inc     edi
0x18001ff9f  mov     [rbp+57h+var_D0], r15
0x18001ffa3  cmp     edi, [rbp+57h+var_C8]
0x18001ffa6  jb      short loc_18001FF2E
0x18001ffa8  mov     eax, [rsi+90h]
0x18001ffae  lea     rcx, [rbp+57h+var_78]
0x18001ffb2  mov     [rbp+57h+var_A0.dwMDIdentifier], eax
0x18001ffb5  mov     eax, [rsi+94h]
0x18001ffbb  mov     [rbp+57h+var_A0.dwMDUserType], eax
0x18001ffbe  mov     eax, [rsi+98h]
0x18001ffc4  mov     [rbp+57h+var_A0.dwMDDataType], eax
0x18001ffc7  mov     eax, [rsi+9Ch]
0x18001ffcd  mov     [rbp+57h+var_A0.dwMDAttributes], eax
0x18001ffd0  mov     dword ptr [rbp+57h+var_A0+14h], r15d
0x18001ffd4  mov     qword ptr [rbp+57h+var_A0.dwMDDataTag], r15
0x18001ffd8  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x18001ffde  lea     rcx, [rbp+57h+var_78]
0x18001ffe2  mov     [rbp+57h+var_A0.pbMDData], rax
0x18001ffe6  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x18001ffec  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001ffef  lea     rdx, [rbp+57h+var_A0]; struct _METADATA_RECORD *
0x18001fff3  mov     rcx, r14; this
0x18001fff6  mov     [rbp+57h+var_A0.dwMDDataLen], eax
0x18001fff9  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001fffe  mov     ebx, eax
0x180020000  jmp     short loc_18002001E
0x180020002  call    cs:__imp_GetLastError
0x180020008  mov     ebx, eax
0x18002000a  test    eax, eax
0x18002000c  jle     short loc_18002001E
0x18002000e  movzx   ebx, ax
0x180020011  or      ebx, 80070000h
0x180020017  jmp     short loc_18002001E
0x180020019  mov     ebx, 80070057h
0x18002001e  mov     rcx, [rbp+57h+var_C0]
0x180020022  test    rcx, rcx
0x180020025  jz      short loc_180020037
0x180020027  mov     rax, [rcx]
0x18002002a  mov     rax, [rax+10h]
0x18002002e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020033  mov     [rbp+57h+var_C0], r15
0x180020037  mov     rcx, [rbp+57h+var_D0]
0x18002003b  test    rcx, rcx
0x18002003e  jz      short loc_180020053
0x180020040  mov     rax, [rcx]
0x180020043  mov     rax, [rax+10h]
0x180020047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002004c  mov     rcx, r15
0x18002004f  mov     [rbp+57h+var_D0], rcx
0x180020053  mov     rdx, [rbp+57h+var_B8]
0x180020057  test    rdx, rdx
0x18002005a  jz      short loc_180020073
0x18002005c  mov     rax, [rdx]
0x18002005f  mov     rcx, rdx
0x180020062  mov     rax, [rax+10h]
0x180020066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002006b  mov     rcx, [rbp+57h+var_D0]
0x18002006f  mov     [rbp+57h+var_B8], r15
0x180020073  mov     rdx, [rbp+57h+var_B0]
0x180020077  test    rdx, rdx
0x18002007a  jz      short loc_180020093
0x18002007c  mov     rax, [rdx]
0x18002007f  mov     rcx, rdx
0x180020082  mov     rax, [rax+10h]
0x180020086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002008b  mov     rcx, [rbp+57h+var_D0]
0x18002008f  mov     [rbp+57h+var_B0], r15
0x180020093  test    rcx, rcx
0x180020096  jz      short loc_1800200A8
0x180020098  mov     rax, [rcx]
0x18002009b  mov     rax, [rax+10h]
0x18002009f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200a4  mov     [rbp+57h+var_D0], r15
0x1800200a8  lea     rcx, [rbp+57h+var_78]
0x1800200ac  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800200b2  mov     eax, ebx
0x1800200b4  mov     rcx, [rbp+57h+var_40]
0x1800200b8  xor     rcx, rsp; StackCookie
0x1800200bb  call    __security_check_cookie
0x1800200c0  add     rsp, 0D8h
0x1800200c7  pop     r15
0x1800200c9  pop     r14
0x1800200cb  pop     rdi
0x1800200cc  pop     rsi
0x1800200cd  pop     rbx
0x1800200ce  pop     rbp
0x1800200cf  retn
```
