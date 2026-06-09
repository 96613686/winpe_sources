# SecureInput::Buffer::Load(void)

- ea: `0x140062ec0`
- end: `0x140063041`
- name: `?Load@Buffer@SecureInput@@QEAAJXZ`
- size: `385`
- prototype: `__int64 __fastcall(SecureInput::Buffer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a660`

## callees

- `0x140002b20`
- `0x140002bc0`
- `0x14000a420`
- `0x14001bd40`
- `0x14002826c`
- `0x140062ec0`
- `0x140063048`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x140062f83`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x140062f83`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140062f38`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140062f38`
- `IumSdk!OpenSecureSection` at `0x140062f08`
- `IumSdk!OpenSecureSection` at `0x140062f08`

## string_xrefs

- `0x140062f54`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140062ff2`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`

## pseudocode

```c
__int64 __fastcall SecureInput::Buffer::Load(SecureInput::Buffer *this)
{
  __int128 v1; // xmm0
  void *v3; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  const void *v6; // rax
  unsigned int LastError; // edi
  int AttributePtr; // eax
  __int64 v9; // rdx
  int dwNumberOfBytesToMap; // [rsp+20h] [rbp-29h]
  char *v12; // [rsp+30h] [rbp-19h] BYREF
  __int64 v13; // [rsp+38h] [rbp-11h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+40h] [rbp-9h] BYREF
  int v15; // [rsp+70h] [rbp+27h] BYREF
  __int128 v16; // [rsp+74h] [rbp+2Bh]
  __int128 v17; // [rsp+84h] [rbp+3Bh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v1 = *((_OWORD *)this + 1);
  v15 = 36;
  v16 = v1;
  v17 = xmmword_140093D20;
  v3 = (void *)OpenSecureSection(&v15);
  *((_QWORD *)this + 5) = v3;
  if ( !v3 )
  {
    v5 = 59;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
                  v4);
LABEL_13:
    SecureInput::Buffer::Unload(this);
    return LastError;
  }
  v6 = MapViewOfFile(v3, 2u, 0, 0, 0);
  *((_QWORD *)this + 6) = v6;
  if ( !v6 )
  {
    v5 = 70;
    goto LABEL_5;
  }
  memset(&Buffer, 0, sizeof(Buffer));
  if ( !VirtualQuery(v6, &Buffer, 0x30u) )
  {
    v5 = 75;
    goto LABEL_5;
  }
  *((_QWORD *)this + 7) = Buffer.RegionSize;
  *((_BYTE *)this + 80) = (Buffer.Protect & 4) != 0;
  AttributePtr = SecureInput::Buffer::Validate(this);
  LastError = AttributePtr;
  if ( AttributePtr < 0 )
  {
    v9 = 80;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
      (const char *)(unsigned int)AttributePtr,
      dwNumberOfBytesToMap);
    goto LABEL_13;
  }
  v12 = 0;
  v13 = 0;
  AttributePtr = SecureInput::Buffer::GetAttributePtr((__int64)this, 0, &v12, &v13);
  LastError = AttributePtr;
  if ( AttributePtr < 0 )
  {
    v9 = 87;
    goto LABEL_12;
  }
  *((_QWORD *)this + 8) = v12;
  *((_QWORD *)this + 9) = v13;
  return 0;
}

```

## disassembly

```asm
0x140062ec0  mov     [rsp-8+arg_8], rbx
0x140062ec5  mov     [rsp-8+arg_10], rdi
0x140062eca  push    rbp
0x140062ecb  lea     rbp, [rsp-57h]
0x140062ed0  sub     rsp, 0A0h
0x140062ed7  mov     rax, cs:__security_cookie
0x140062ede  xor     rax, rsp
0x140062ee1  mov     [rbp+57h+var_8], rax
0x140062ee5  movups  xmm0, xmmword ptr [rcx+10h]
0x140062ee9  mov     rbx, rcx
0x140062eec  lea     rcx, [rbp+57h+var_30]
0x140062ef0  movups  xmm1, cs:xmmword_140093D20
0x140062ef7  mov     [rbp+57h+var_30], 24h ; '$'
0x140062efe  movdqu  [rbp+57h+var_2C], xmm0
0x140062f03  movdqu  [rbp+57h+var_1C], xmm1
0x140062f08  call    cs:__imp_OpenSecureSection
0x140062f0f  nop     dword ptr [rax+rax+00h]
0x140062f14  mov     [rbx+28h], rax
0x140062f18  test    rax, rax
0x140062f1b  jnz     short loc_140062F22
0x140062f1d  lea     edx, [rax+3Bh]
0x140062f20  jmp     short loc_140062F50
0x140062f22  xor     r9d, r9d; dwFileOffsetLow
0x140062f25  mov     qword ptr [rsp+0A0h+dwNumberOfBytesToMap], 0; int
0x140062f2e  xor     r8d, r8d; dwFileOffsetHigh
0x140062f31  mov     rcx, rax; hFileMappingObject
0x140062f34  lea     edx, [r9+2]; dwDesiredAccess
0x140062f38  call    cs:__imp_MapViewOfFile
0x140062f3f  nop     dword ptr [rax+rax+00h]
0x140062f44  mov     [rbx+30h], rax
0x140062f48  test    rax, rax
0x140062f4b  jnz     short loc_140062F67
0x140062f4d  lea     edx, [rax+46h]; void *
0x140062f50  mov     rcx, [rbp+5Fh]; this
0x140062f54  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140062f5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140062f60  mov     edi, eax
0x140062f62  jmp     loc_140063001
0x140062f67  xorps   xmm0, xmm0
0x140062f6a  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x140062f6e  mov     r8d, 30h ; '0'; dwLength
0x140062f74  mov     rcx, rax; lpAddress
0x140062f77  movups  xmmword ptr [rbp+57h+Buffer.BaseAddress], xmm0
0x140062f7b  movups  xmmword ptr [rbp+57h+Buffer.AllocationProtect], xmm0
0x140062f7f  movups  xmmword ptr [rbp+57h+Buffer.State], xmm0
0x140062f83  call    cs:__imp_VirtualQuery
0x140062f8a  nop     dword ptr [rax+rax+00h]
0x140062f8f  test    rax, rax
0x140062f92  jnz     short loc_140062F99
0x140062f94  lea     edx, [rax+4Bh]
0x140062f97  jmp     short loc_140062F50
0x140062f99  mov     rax, [rbp+57h+Buffer.RegionSize]
0x140062f9d  mov     rcx, rbx; this
0x140062fa0  mov     [rbx+38h], rax
0x140062fa4  mov     eax, [rbp+57h+Buffer.Protect]
0x140062fa7  shr     eax, 2
0x140062faa  and     al, 1
0x140062fac  mov     [rbx+50h], al
0x140062faf  call    ?Validate@Buffer@SecureInput@@AEBAJXZ; SecureInput::Buffer::Validate(void)
0x140062fb4  mov     edi, eax
0x140062fb6  test    eax, eax
0x140062fb8  jns     short loc_140062FC1
0x140062fba  mov     edx, 50h ; 'P'
0x140062fbf  jmp     short loc_140062FEE
0x140062fc1  lea     r9, [rbp+57h+var_68]
0x140062fc5  mov     [rbp+57h+var_70], 0
0x140062fcd  lea     r8, [rbp+57h+var_70]
0x140062fd1  mov     [rbp+57h+var_68], 0
0x140062fd9  xor     edx, edx
0x140062fdb  mov     rcx, rbx
0x140062fde  call    ?GetAttributePtr@Buffer@SecureInput@@AEBAJW4_IUM_SECURE_BUFFER_ATTRIBUTE_ID@@PEAPEAEPEA_K@Z; SecureInput::Buffer::GetAttributePtr(_IUM_SECURE_BUFFER_ATTRIBUTE_ID,uchar * *,unsigned __int64 *)
0x140062fe3  mov     edi, eax
0x140062fe5  test    eax, eax
0x140062fe7  jns     short loc_14006300D
0x140062fe9  mov     edx, 57h ; 'W'; void *
0x140062fee  mov     rcx, [rbp+5Fh]; this
0x140062ff2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140062ff9  mov     r9d, eax; char *
0x140062ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140063001  mov     rcx, rbx; this
0x140063004  call    ?Unload@Buffer@SecureInput@@QEAAXXZ; SecureInput::Buffer::Unload(void)
0x140063009  mov     eax, edi
0x14006300b  jmp     short loc_14006301F
0x14006300d  mov     rax, [rbp+57h+var_70]
0x140063011  mov     [rbx+40h], rax
0x140063015  mov     rax, [rbp+57h+var_68]
0x140063019  mov     [rbx+48h], rax
0x14006301d  xor     eax, eax
0x14006301f  mov     rcx, [rbp+57h+var_8]
0x140063023  xor     rcx, rsp; StackCookie
0x140063026  call    __security_check_cookie
0x14006302b  lea     r11, [rsp+0A0h+var_s0]
0x140063033  mov     rbx, [r11+18h]
0x140063037  mov     rdi, [r11+20h]
0x14006303b  mov     rsp, r11
0x14006303e  pop     rbp
0x14006303f  retn
```
