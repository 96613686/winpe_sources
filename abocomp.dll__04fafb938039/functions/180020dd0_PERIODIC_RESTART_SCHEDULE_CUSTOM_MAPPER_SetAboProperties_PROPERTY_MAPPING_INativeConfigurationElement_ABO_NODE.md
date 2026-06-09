# PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x180020dd0`
- end: `0x18002106d`
- name: `?SetAboProperties@PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `669`
- prototype: `int(PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002990`
- `0x1800029d0`
- `0x180003460`
- `0x18000a838`
- `0x180020dd0`
- `0x180029960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002100e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002100e`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180020e21`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180020e21`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x180020f94`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x180020f94`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180020f19`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180020f19`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x180020fa2`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x180020fa2`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002103e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002103e`

## pseudocode

```c
__int64 __fastcall PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER::SetAboProperties(
        PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  void *v4; // rsi
  TIMESPAN_PARSER *v8; // rdi
  signed int v9; // ebx
  unsigned int v10; // r15d
  int v11; // eax
  signed int LastError; // eax
  unsigned int v14; // [rsp+30h] [rbp-69h] BYREF
  __int64 v15; // [rsp+38h] [rbp-61h] BYREF
  __int64 v16; // [rsp+40h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  __int64 v18; // [rsp+50h] [rbp-49h] BYREF
  struct _METADATA_RECORD v19; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v20[56]; // [rsp+80h] [rbp-19h] BYREF

  v15 = 0;
  v4 = 0;
  v16 = 0;
  v14 = 0;
  pv = 0;
  v18 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v20);
  v8 = 0;
  if ( a2 && a3 && a4 )
  {
    v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v16);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 24LL))(v16, &v14);
      if ( v9 >= 0 )
      {
        v10 = 0;
        if ( v14 )
        {
          while ( 1 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 32LL))(v16, v10, &v15);
            if ( v9 < 0 )
              goto LABEL_18;
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v15 + 80LL))(
                   v15,
                   L"value",
                   &v18,
                   0,
                   0);
            if ( v9 < 0 )
              goto LABEL_18;
            v8 = (TIMESPAN_PARSER *)operator new(8u);
            if ( !v8 )
            {
              v9 = -2147024888;
LABEL_18:
              v8 = 0;
              goto LABEL_20;
            }
            *(_QWORD *)v8 = v18;
            v11 = TIMESPAN_PARSER::GetInHHMM(v8, (unsigned __int16 **)&pv);
            v4 = pv;
            v9 = v11;
            if ( v11 < 0 )
              goto LABEL_20;
            if ( !MULTISZ::Append((MULTISZ *)v20, (const unsigned __int16 *)pv) )
              break;
            operator delete(v8);
            CoTaskMemFree(v4);
            v4 = 0;
            pv = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            ++v10;
            v15 = 0;
            if ( v10 >= v14 )
              goto LABEL_13;
          }
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
LABEL_13:
          v19.dwMDIdentifier = *((_DWORD *)a2 + 36);
          v19.dwMDUserType = *((_DWORD *)a2 + 37);
          v19.dwMDDataType = *((_DWORD *)a2 + 38);
          v19.dwMDAttributes = *((_DWORD *)a2 + 39);
          *(&v19.dwMDDataLen + 1) = 0;
          *(_QWORD *)&v19.dwMDDataTag = 0;
          v19.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v20);
          v8 = 0;
          v19.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v20);
          if ( v14 )
            v9 = ABO_NODE::SetDataByMapping(a4, &v19, a2);
        }
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_20:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v8 )
    operator delete(v8);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180020dd0  mov     [rsp-8+arg_0], rbx
0x180020dd5  push    rbp
0x180020dd6  push    rsi
0x180020dd7  push    rdi
0x180020dd8  push    r12
0x180020dda  push    r13
0x180020ddc  push    r14
0x180020dde  push    r15
0x180020de0  lea     rbp, [rsp-27h]
0x180020de5  sub     rsp, 0C0h
0x180020dec  mov     rax, cs:__security_cookie
0x180020df3  xor     rax, rsp
0x180020df6  mov     [rbp+57h+var_38], rax
0x180020dfa  xor     r13d, r13d
0x180020dfd  lea     rcx, [rbp+57h+var_70]
0x180020e01  mov     [rbp+57h+var_B8], r13
0x180020e05  mov     esi, r13d
0x180020e08  mov     [rbp+57h+var_B0], r13
0x180020e0c  mov     r12, r9
0x180020e0f  mov     [rbp+57h+var_C0], r13d
0x180020e13  mov     rbx, r8
0x180020e16  mov     [rbp+57h+pv], r13
0x180020e1a  mov     r14, rdx
0x180020e1d  mov     [rbp+57h+var_A0], r13
0x180020e21  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180020e27  mov     edi, r13d
0x180020e2a  test    r14, r14
0x180020e2d  jz      loc_180020FE8
0x180020e33  test    rbx, rbx
0x180020e36  jz      loc_180020FE8
0x180020e3c  test    r12, r12
0x180020e3f  jz      loc_180020FE8
0x180020e45  mov     rax, [rbx]
0x180020e48  lea     rdx, [rbp+57h+var_B0]
0x180020e4c  mov     rcx, rbx
0x180020e4f  mov     rax, [rax+28h]
0x180020e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e58  mov     ebx, eax
0x180020e5a  test    eax, eax
0x180020e5c  js      loc_180020FED
0x180020e62  mov     rcx, [rbp+57h+var_B0]
0x180020e66  lea     rdx, [rbp+57h+var_C0]
0x180020e6a  mov     rax, [rcx]
0x180020e6d  mov     rax, [rax+18h]
0x180020e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e76  mov     ebx, eax
0x180020e78  test    eax, eax
0x180020e7a  js      loc_180020FED
0x180020e80  mov     r15d, r13d
0x180020e83  cmp     [rbp+57h+var_C0], r13d
0x180020e87  jbe     loc_180020F60
0x180020e8d  mov     rcx, [rbp+57h+var_B0]
0x180020e91  lea     r8, [rbp+57h+var_B8]
0x180020e95  mov     edx, r15d
0x180020e98  mov     rax, [rcx]
0x180020e9b  mov     rax, [rax+20h]
0x180020e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ea4  mov     ebx, eax
0x180020ea6  test    eax, eax
0x180020ea8  js      loc_180020FE3
0x180020eae  mov     rcx, [rbp+57h+var_B8]
0x180020eb2  lea     r8, [rbp+57h+var_A0]
0x180020eb6  xor     r9d, r9d
0x180020eb9  mov     [rsp+0F0h+var_D0], r13
0x180020ebe  lea     rdx, aValue; "value"
0x180020ec5  mov     rax, [rcx]
0x180020ec8  mov     rax, [rax+50h]
0x180020ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ed1  mov     ebx, eax
0x180020ed3  test    eax, eax
0x180020ed5  js      loc_180020FE3
0x180020edb  mov     ecx, 8; Size
0x180020ee0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020ee5  mov     rdi, rax
0x180020ee8  test    rax, rax
0x180020eeb  jz      loc_180020FDE
0x180020ef1  mov     rax, [rbp+57h+var_A0]
0x180020ef5  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x180020ef9  mov     rcx, rdi; this
0x180020efc  mov     [rdi], rax
0x180020eff  call    ?GetInHHMM@TIMESPAN_PARSER@@QEAAJPEAPEAG@Z; TIMESPAN_PARSER::GetInHHMM(ushort * *)
0x180020f04  mov     rsi, [rbp+57h+pv]
0x180020f08  mov     ebx, eax
0x180020f0a  test    eax, eax
0x180020f0c  js      loc_180020FED
0x180020f12  mov     rdx, rsi
0x180020f15  lea     rcx, [rbp+57h+var_70]
0x180020f19  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180020f1f  test    eax, eax
0x180020f21  jz      loc_180020FC7
0x180020f27  mov     rcx, rdi; Block
0x180020f2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020f2f  mov     rcx, rsi; pv
0x180020f32  call    cs:__imp_CoTaskMemFree
0x180020f38  mov     rcx, [rbp+57h+var_B8]
0x180020f3c  mov     rsi, r13
0x180020f3f  mov     [rbp+57h+pv], r13
0x180020f43  mov     rax, [rcx]
0x180020f46  mov     rax, [rax+10h]
0x180020f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f4f  inc     r15d
0x180020f52  mov     [rbp+57h+var_B8], r13
0x180020f56  cmp     r15d, [rbp+57h+var_C0]
0x180020f5a  jb      loc_180020E8D
0x180020f60  mov     eax, [r14+90h]
0x180020f67  lea     rcx, [rbp+57h+var_70]
0x180020f6b  mov     [rbp+57h+var_98.dwMDIdentifier], eax
0x180020f6e  mov     eax, [r14+94h]
0x180020f75  mov     [rbp+57h+var_98.dwMDUserType], eax
0x180020f78  mov     eax, [r14+98h]
0x180020f7f  mov     [rbp+57h+var_98.dwMDDataType], eax
0x180020f82  mov     eax, [r14+9Ch]
0x180020f89  mov     [rbp+57h+var_98.dwMDAttributes], eax
0x180020f8c  mov     dword ptr [rbp+57h+var_98+14h], r13d
0x180020f90  mov     qword ptr [rbp+57h+var_98.dwMDDataTag], r13
0x180020f94  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180020f9a  lea     rcx, [rbp+57h+var_70]
0x180020f9e  mov     [rbp+57h+var_98.pbMDData], rax
0x180020fa2  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x180020fa8  mov     rdi, r13
0x180020fab  mov     [rbp+57h+var_98.dwMDDataLen], eax
0x180020fae  cmp     [rbp+57h+var_C0], r13d
0x180020fb2  jbe     short loc_180020FED
0x180020fb4  mov     r8, r14; struct PROPERTY_MAPPING *
0x180020fb7  lea     rdx, [rbp+57h+var_98]; struct _METADATA_RECORD *
0x180020fbb  mov     rcx, r12; this
0x180020fbe  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x180020fc3  mov     ebx, eax
0x180020fc5  jmp     short loc_180020FED
0x180020fc7  call    cs:__imp_GetLastError
0x180020fcd  mov     ebx, eax
0x180020fcf  test    eax, eax
0x180020fd1  jle     short loc_180020FED
0x180020fd3  movzx   ebx, ax
0x180020fd6  or      ebx, 80070000h
0x180020fdc  jmp     short loc_180020FED
0x180020fde  mov     ebx, 80070008h
0x180020fe3  mov     rdi, r13
0x180020fe6  jmp     short loc_180020FED
0x180020fe8  mov     ebx, 80070057h
0x180020fed  mov     rcx, [rbp+57h+var_B0]
0x180020ff1  test    rcx, rcx
0x180020ff4  jz      short loc_180021006
0x180020ff6  mov     rax, [rcx]
0x180020ff9  mov     rax, [rax+10h]
0x180020ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021002  mov     [rbp+57h+var_B0], r13
0x180021006  test    rsi, rsi
0x180021009  jz      short loc_180021014
0x18002100b  mov     rcx, rsi; pv
0x18002100e  call    cs:__imp_CoTaskMemFree
0x180021014  test    rdi, rdi
0x180021017  jz      short loc_180021021
0x180021019  mov     rcx, rdi; Block
0x18002101c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021021  mov     rcx, [rbp+57h+var_B8]
0x180021025  test    rcx, rcx
0x180021028  jz      short loc_18002103A
0x18002102a  mov     rax, [rcx]
0x18002102d  mov     rax, [rax+10h]
0x180021031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021036  mov     [rbp+57h+var_B8], r13
0x18002103a  lea     rcx, [rbp+57h+var_70]
0x18002103e  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180021044  mov     eax, ebx
0x180021046  mov     rcx, [rbp+57h+var_38]
0x18002104a  xor     rcx, rsp; StackCookie
0x18002104d  call    __security_check_cookie
0x180021052  mov     rbx, [rsp+0F0h+arg_0]
0x18002105a  add     rsp, 0C0h
0x180021061  pop     r15
0x180021063  pop     r14
0x180021065  pop     r13
0x180021067  pop     r12
0x180021069  pop     rdi
0x18002106a  pop     rsi
0x18002106b  pop     rbp
0x18002106c  retn
```
