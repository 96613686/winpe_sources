# GetUriStringFromDialString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800c4e60`
- end: `0x1800c5096`
- name: `?GetUriStringFromDialString@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `566`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1e90`
- `0x1800c4500`

## callees

- `0x18000b7fc`
- `0x18005bc20`
- `0x1800c4e60`
- `0x1800c509c`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `PhoneUtil!MaskPhoneUri` at `0x1800c4f8f`
- `PhoneUtil!MaskPhoneUri` at `0x1800c4f8f`
- `PhoneUtil!GetTelUriFromDialString` at `0x1800c4f1f`
- `PhoneUtil!GetTelUriFromDialString` at `0x1800c4f1f`
- `PhoneUtil!MaskPhoneNumber` at `0x1800c4f64`
- `PhoneUtil!MaskPhoneNumber` at `0x1800c4f64`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x1800c4e9f`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x1800c4e9f`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x1800c4ee1`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x1800c4ee1`

## pseudocode

```c
__int64 __fastcall GetUriStringFromDialString(const unsigned __int16 *a1, __int64 a2)
{
  int DefaultOutgoingLine; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int128 v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[128]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v17[96]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v18[16]; // [rsp+180h] [rbp+80h] BYREF
  _WORD *v19; // [rsp+190h] [rbp+90h]
  int v20; // [rsp+198h] [rbp+98h]
  int v21; // [rsp+19Ch] [rbp+9Ch]
  _WORD *v22; // [rsp+1A0h] [rbp+A0h]
  int v23; // [rsp+1A8h] [rbp+A8h]
  int v24; // [rsp+1ACh] [rbp+ACh]
  unsigned __int16 v25[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  _WORD v26[64]; // [rsp+230h] [rbp+130h] BYREF
  _WORD v27[64]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v15 = 0;
  DefaultOutgoingLine = PhoneGetDefaultOutgoingLine(&v15);
  if ( DefaultOutgoingLine < 0 )
  {
    v6 = 54;
LABEL_3:
    v7 = 1;
LABEL_4:
    Log_HREvent_103((unsigned int)DefaultOutgoingLine, v7, v5, v6);
    return (unsigned int)DefaultOutgoingLine;
  }
  memset_0(v16, 0, 0x13Cu);
  DefaultOutgoingLine = PhoneGetProviderLineServiceInfo(&v15, v16);
  if ( DefaultOutgoingLine < 0 )
  {
    v6 = 57;
    goto LABEL_3;
  }
  memset_0(v25, 0, sizeof(v25));
  DefaultOutgoingLine = GetTelUriFromDialString(a1, v17, v25, 0x40u);
  if ( DefaultOutgoingLine < 0 )
  {
    v6 = 61;
    goto LABEL_3;
  }
  memset_0(v26, 0, sizeof(v26));
  memset_0(v27, 0, sizeof(v27));
  v9 = MaskPhoneNumber(a1, v26, 64);
  if ( v9 < 0 )
    Log_HREvent_103((unsigned int)v9, 0, v10, 65);
  MaskPhoneUri(v25, v27, 64);
  v12 = -1;
  if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v26[v13] );
    v21 = 0;
    v20 = 2 * v13 + 2;
    v19 = v26;
    v14 = -1;
    do
      ++v14;
    while ( v27[v14] );
    v24 = 0;
    v23 = 2 * v14 + 2;
    v22 = v27;
    McGenEventWrite_EventWriteTransfer(
      MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context,
      UtilsTelUriConvert,
      v11,
      3,
      v18);
  }
  do
    ++v12;
  while ( v25[v12] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a2,
                           v25,
                           v12) )
  {
    v7 = 0;
    DefaultOutgoingLine = -2147024882;
    v6 = 69;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800c4e60  mov     [rsp-8+arg_10], rbx
0x1800c4e65  push    rbp
0x1800c4e66  push    rsi
0x1800c4e67  push    rdi
0x1800c4e68  push    r12
0x1800c4e6a  push    r14
0x1800c4e6c  lea     rbp, [rsp-240h]
0x1800c4e74  sub     rsp, 340h
0x1800c4e7b  mov     rax, cs:__security_cookie
0x1800c4e82  xor     rax, rsp
0x1800c4e85  mov     [rbp+260h+var_30], rax
0x1800c4e8c  mov     rdi, rcx
0x1800c4e8f  xorps   xmm0, xmm0
0x1800c4e92  lea     rcx, [rsp+360h+var_330]
0x1800c4e97  mov     rsi, rdx
0x1800c4e9a  movups  [rsp+360h+var_330], xmm0
0x1800c4e9f  call    cs:__imp_PhoneGetDefaultOutgoingLine
0x1800c4ea5  xor     r14d, r14d
0x1800c4ea8  mov     ebx, eax
0x1800c4eaa  test    eax, eax
0x1800c4eac  jns     short loc_1800C4EC5
0x1800c4eae  lea     r9d, [r14+36h]
0x1800c4eb2  mov     edx, 1
0x1800c4eb7  mov     ecx, ebx
0x1800c4eb9  call    Log_HREvent_103
0x1800c4ebe  mov     eax, ebx
0x1800c4ec0  jmp     loc_1800C5070
0x1800c4ec5  xor     edx, edx; Val
0x1800c4ec7  lea     rcx, [rsp+360h+var_320]; void *
0x1800c4ecc  mov     r8d, 13Ch; Size
0x1800c4ed2  call    memset_0
0x1800c4ed7  lea     rdx, [rsp+360h+var_320]
0x1800c4edc  lea     rcx, [rsp+360h+var_330]
0x1800c4ee1  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x1800c4ee7  mov     ebx, eax
0x1800c4ee9  test    eax, eax
0x1800c4eeb  jns     short loc_1800C4EF5
0x1800c4eed  mov     r9d, 39h ; '9'
0x1800c4ef3  jmp     short loc_1800C4EB2
0x1800c4ef5  mov     r12d, 80h
0x1800c4efb  lea     rcx, [rbp+260h+var_1B0]; void *
0x1800c4f02  mov     r8d, r12d; Size
0x1800c4f05  xor     edx, edx; Val
0x1800c4f07  call    memset_0
0x1800c4f0c  lea     r9d, [r12-40h]
0x1800c4f11  mov     rcx, rdi
0x1800c4f14  lea     r8, [rbp+260h+var_1B0]
0x1800c4f1b  lea     rdx, [rbp+260h+var_2A0]
0x1800c4f1f  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x1800c4f25  mov     ebx, eax
0x1800c4f27  test    eax, eax
0x1800c4f29  jns     short loc_1800C4F32
0x1800c4f2b  lea     r9d, [r12-43h]
0x1800c4f30  jmp     short loc_1800C4EB2
0x1800c4f32  mov     r8, r12; Size
0x1800c4f35  lea     rcx, [rbp+260h+var_130]; void *
0x1800c4f3c  xor     edx, edx; Val
0x1800c4f3e  call    memset_0
0x1800c4f43  mov     r8, r12; Size
0x1800c4f46  lea     rcx, [rbp+260h+var_B0]; void *
0x1800c4f4d  xor     edx, edx; Val
0x1800c4f4f  call    memset_0
0x1800c4f54  mov     r8d, 40h ; '@'
0x1800c4f5a  lea     rdx, [rbp+260h+var_130]
0x1800c4f61  mov     rcx, rdi
0x1800c4f64  call    cs:__imp_MaskPhoneNumber
0x1800c4f6a  test    eax, eax
0x1800c4f6c  jns     short loc_1800C4F7B
0x1800c4f6e  xor     edx, edx
0x1800c4f70  mov     ecx, eax
0x1800c4f72  lea     r9d, [rdx+41h]
0x1800c4f76  call    Log_HREvent_103
0x1800c4f7b  mov     r8d, 40h ; '@'
0x1800c4f81  lea     rdx, [rbp+260h+var_B0]
0x1800c4f88  lea     rcx, [rbp+260h+var_1B0]
0x1800c4f8f  call    cs:__imp_MaskPhoneUri
0x1800c4f95  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c4f99  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x1800c4fa0  jz      loc_1800C5037
0x1800c4fa6  lea     rcx, [rbp+260h+var_130]
0x1800c4fad  mov     rax, rbx
0x1800c4fb0  inc     rax
0x1800c4fb3  cmp     [rcx+rax*2], r14w
0x1800c4fb8  jnz     short loc_1800C4FB0
0x1800c4fba  lea     eax, ds:2[rax*2]
0x1800c4fc1  mov     [rbp+260h+var_1C4], r14d
0x1800c4fc8  lea     rcx, [rbp+260h+var_130]
0x1800c4fcf  mov     [rbp+260h+var_1C8], eax
0x1800c4fd5  mov     [rbp+260h+var_1D0], rcx
0x1800c4fdc  mov     rax, rbx
0x1800c4fdf  lea     rcx, [rbp+260h+var_B0]
0x1800c4fe6  inc     rax
0x1800c4fe9  cmp     [rcx+rax*2], r14w
0x1800c4fee  jnz     short loc_1800C4FE6
0x1800c4ff0  lea     eax, ds:2[rax*2]
0x1800c4ff7  mov     [rbp+260h+var_1B4], r14d
0x1800c4ffe  lea     rcx, [rbp+260h+var_B0]
0x1800c5005  mov     [rbp+260h+var_1B8], eax
0x1800c500b  lea     rax, [rbp+260h+var_1E0]
0x1800c5012  mov     [rbp+260h+var_1C0], rcx
0x1800c5019  mov     r9d, 3
0x1800c501f  mov     [rsp+360h+var_340], rax
0x1800c5024  lea     rdx, UtilsTelUriConvert
0x1800c502b  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context
0x1800c5032  call    McGenEventWrite_EventWriteTransfer
0x1800c5037  lea     rax, [rbp+260h+var_1B0]
0x1800c503e  inc     rbx
0x1800c5041  cmp     [rax+rbx*2], r14w
0x1800c5046  jnz     short loc_1800C503E
0x1800c5048  mov     r8, rbx
0x1800c504b  lea     rdx, [rbp+260h+var_1B0]
0x1800c5052  mov     rcx, rsi
0x1800c5055  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800c505a  test    al, al
0x1800c505c  jnz     short loc_1800C506E
0x1800c505e  xor     edx, edx
0x1800c5060  mov     ebx, 8007000Eh
0x1800c5065  lea     r9d, [rdx+45h]
0x1800c5069  jmp     loc_1800C4EB7
0x1800c506e  xor     eax, eax
0x1800c5070  mov     rcx, [rbp+260h+var_30]
0x1800c5077  xor     rcx, rsp; StackCookie
0x1800c507a  call    __security_check_cookie
0x1800c507f  mov     rbx, [rsp+360h+arg_10]
0x1800c5087  add     rsp, 340h
0x1800c508e  pop     r14
0x1800c5090  pop     r12
0x1800c5092  pop     rdi
0x1800c5093  pop     rsi
0x1800c5094  pop     rbp
0x1800c5095  retn
```
