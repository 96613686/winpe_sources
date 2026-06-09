# CBleMidiEndpointBuilder::GetBleMidiCapabilities(ushort const *,uchar *,uchar *)

- ea: `0x1800565dc`
- end: `0x1800568ff`
- name: `?GetBleMidiCapabilities@CBleMidiEndpointBuilder@@SAJPEBGPEAE1@Z`
- size: `803`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x180056ad4`

## callees

- `0x18000128c`
- `0x180002314`
- `0x18001f374`
- `0x18003e920`
- `0x18003f780`
- `0x18003f7a4`
- `0x1800565dc`
- `0x180065070`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005672d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005672d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180056692`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180056692`
- `ext-ms-win-bluetooth-apis-l1-1-0!BluetoothGATTGetCharacteristics` at `0x18005675d`
- `ext-ms-win-bluetooth-apis-l1-1-0!BluetoothGATTGetCharacteristics` at `0x18005675d`
- `ext-ms-win-bluetooth-apis-l1-1-0!BluetoothGATTGetServices` at `0x1800566b4`
- `ext-ms-win-bluetooth-apis-l1-1-0!BluetoothGATTGetServices` at `0x1800566b4`

## pseudocode

```c
__int64 __fastcall CBleMidiEndpointBuilder::GetBleMidiCapabilities(
        const unsigned __int16 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3)
{
  int v6; // ebx
  HANDLE FileW; // rax
  void *v8; // rdi
  int v9; // eax
  int v10; // esi
  int v11; // ebx
  int v12; // r15d
  int v13; // esi
  _WORD *v14; // rsi
  const struct _tlgProvider_t *v15; // rax
  int v16; // r9d
  char v17; // cl
  const struct _tlgProvider_t *v18; // rax
  int v19; // r8d
  int v20; // r9d
  char v22; // [rsp+70h] [rbp-90h] BYREF
  char v23; // [rsp+71h] [rbp-8Fh] BYREF
  char v24; // [rsp+72h] [rbp-8Eh] BYREF
  char v25; // [rsp+73h] [rbp-8Dh] BYREF
  char v26; // [rsp+74h] [rbp-8Ch] BYREF
  char v27; // [rsp+75h] [rbp-8Bh] BYREF
  _BYTE v28[2]; // [rsp+76h] [rbp-8Ah] BYREF
  _WORD v29[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v30; // [rsp+7Ch] [rbp-84h] BYREF
  __int16 v31; // [rsp+80h] [rbp-80h] BYREF
  __int16 v32; // [rsp+82h] [rbp-7Eh] BYREF
  _DWORD v33[3]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE v34[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v35[59]; // [rsp+94h] [rbp-6Ch] BYREF
  _WORD v36[2]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v37[3596]; // [rsp+274h] [rbp+174h] BYREF

  v34[0] = 0;
  memset_0(v35, 0, 0x1DCu);
  v29[0] = 0;
  v36[0] = 0;
  memset_0(v37, 0, sizeof(v37));
  v30 = 0;
  if ( !a2 || !a3 )
  {
    v6 = -2147467261;
    goto LABEL_26;
  }
  *a2 = 0;
  v6 = 0;
  *a3 = 0;
  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v9 = BluetoothGATTGetServices(FileW, 20, v34, v29, 0);
    v6 = v9;
    if ( v9 == -2147024895 )
    {
      v6 = -2147418113;
    }
    else if ( v9 >= 0 )
    {
      v10 = v29[0];
      v11 = 0;
      if ( !v29[0] )
        goto LABEL_11;
      while ( v34[24 * v11] || memcmp_0(&v35[3 * v11], &GUID_03b80e5a_ede8_4b33_a751_6ce34ec4c700, 0x10u) )
      {
        if ( ++v11 >= v10 )
          goto LABEL_11;
      }
      v6 = BluetoothGATTGetCharacteristics(v8, &v34[24 * v11], 100, v36, &v30, 0);
      if ( v6 < 0 )
        goto LABEL_12;
      v12 = v30;
      v13 = 0;
      if ( !v30 )
        goto LABEL_11;
      while ( v37[36 * v13] || memcmp_0(&v37[36 * v13 + 4], &GUID_7772e5db_3868_4112_a1a9_f2669d106bf3, 0x10u) )
      {
        if ( ++v13 >= v12 )
          goto LABEL_11;
      }
      v14 = &v36[18 * v13];
      if ( v14 )
      {
        v15 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v15 > 4u )
        {
          v17 = *((_BYTE *)v14 + 34);
          v26 = *((_BYTE *)v14 + 30);
          v27 = *((_BYTE *)v14 + 29);
          v28[0] = *((_BYTE *)v14 + 28);
          v31 = v14[13];
          v32 = v14[12];
          LOWORD(v33[0]) = *v14;
          v22 = v17;
          v23 = *((_BYTE *)v14 + 33);
          v24 = *((_BYTE *)v14 + 32);
          v25 = *((_BYTE *)v14 + 31);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
            (_DWORD)v15,
            (unsigned int)&byte_180077107,
            (_DWORD)v15,
            v16,
            (__int64)v33,
            (__int64)&v32,
            (__int64)&v31,
            (__int64)v28,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v23,
            (__int64)&v22);
        }
        *a2 = *((_BYTE *)v14 + 29);
        *a3 = *((_BYTE *)v14 + 31);
      }
      else
      {
LABEL_11:
        v6 = -2147023728;
      }
    }
  }
LABEL_12:
  if ( v8 && v8 != (void *)-1LL )
    CloseHandle(v8);
LABEL_26:
  v18 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v18 > 4u )
  {
    v33[0] = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v18,
      (unsigned int)&word_1800770BE,
      v19,
      v20,
      (__int64)v33);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800565dc  mov     [rsp-8+arg_18], rbx
0x1800565e1  push    rbp
0x1800565e2  push    rsi
0x1800565e3  push    rdi
0x1800565e4  push    r12
0x1800565e6  push    r13
0x1800565e8  push    r14
0x1800565ea  push    r15
0x1800565ec  lea     rbp, [rsp-0F90h]
0x1800565f4  mov     eax, 1090h
0x1800565f9  call    _alloca_probe
0x1800565fe  sub     rsp, rax
0x180056601  mov     rax, cs:__security_cookie
0x180056608  xor     rax, rsp
0x18005660b  mov     [rbp+0FC0h+var_40], rax
0x180056612  mov     r12, r8
0x180056615  mov     [rbp+0FC0h+var_1030], 0
0x180056619  mov     r13, rdx
0x18005661c  mov     rdi, rcx
0x18005661f  xor     edx, edx; Val
0x180056621  lea     rcx, [rbp+0FC0h+var_102C]; void *
0x180056625  mov     r8d, 1DCh; Size
0x18005662b  call    memset_0
0x180056630  xor     eax, eax
0x180056632  lea     rcx, [rbp+0FC0h+var_E4C]; void *
0x180056639  xor     edx, edx; Val
0x18005663b  mov     [rsp+10C0h+var_1048], ax
0x180056640  mov     r8d, 0E0Ch; Size
0x180056646  mov     [rbp+0FC0h+var_E50], ax
0x18005664d  call    memset_0
0x180056652  xor     eax, eax
0x180056654  mov     [rsp+10C0h+var_1044], ax
0x180056659  test    r13, r13
0x18005665c  jz      loc_1800568A7
0x180056662  test    r12, r12
0x180056665  jz      loc_1800568A7
0x18005666b  mov     [rsp+10C0h+hTemplateFile], rax; hTemplateFile
0x180056670  lea     r8d, [rax+3]; dwShareMode
0x180056674  mov     [rsp+10C0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180056678  xor     r9d, r9d; lpSecurityAttributes
0x18005667b  mov     [r13+0], al
0x18005667f  mov     edx, 0C0000000h; dwDesiredAccess
0x180056684  mov     rcx, rdi; lpFileName
0x180056687  mov     [rsp+10C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005668c  xor     ebx, ebx
0x18005668e  mov     [r12], al
0x180056692  call    cs:__imp_CreateFileW
0x180056698  mov     rdi, rax
0x18005669b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005669f  jz      short loc_180056717
0x1800566a1  lea     edx, [rbx+14h]
0x1800566a4  mov     [rsp+10C0h+dwCreationDisposition], ebx
0x1800566a8  lea     r9, [rsp+10C0h+var_1048]
0x1800566ad  mov     rcx, rax
0x1800566b0  lea     r8, [rbp+0FC0h+var_1030]
0x1800566b4  call    cs:__imp_BluetoothGATTGetServices
0x1800566ba  mov     ebx, eax
0x1800566bc  cmp     eax, 80070001h
0x1800566c1  jnz     short loc_1800566CA
0x1800566c3  mov     ebx, 8000FFFFh
0x1800566c8  jmp     short loc_180056717
0x1800566ca  test    eax, eax
0x1800566cc  js      short loc_180056717
0x1800566ce  movzx   esi, [rsp+10C0h+var_1048]
0x1800566d3  xor     ebx, ebx
0x1800566d5  test    esi, esi
0x1800566d7  jz      short loc_180056712
0x1800566d9  movsxd  rax, ebx
0x1800566dc  lea     r14, [rbp+0FC0h+var_1030]
0x1800566e0  lea     rcx, [rax+rax*2]
0x1800566e4  lea     r14, [r14+rcx*8]
0x1800566e8  cmp     byte ptr [r14], 0
0x1800566ec  jnz     short loc_18005670C
0x1800566ee  lea     rax, [rbp+0FC0h+var_102C]
0x1800566f2  mov     r8d, 10h; Size
0x1800566f8  lea     rcx, [rax+rcx*8]; Buf1
0x1800566fc  lea     rdx, _GUID_03b80e5a_ede8_4b33_a751_6ce34ec4c700; Buf2
0x180056703  call    memcmp_0
0x180056708  test    eax, eax
0x18005670a  jz      short loc_180056738
0x18005670c  inc     ebx
0x18005670e  cmp     ebx, esi
0x180056710  jl      short loc_1800566D9
0x180056712  mov     ebx, 80070490h
0x180056717  test    rdi, rdi
0x18005671a  jz      loc_1800568AC
0x180056720  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180056724  jz      loc_1800568AC
0x18005672a  mov     rcx, rdi; hObject
0x18005672d  call    cs:__imp_CloseHandle
0x180056733  jmp     loc_1800568AC
0x180056738  lea     rax, [rsp+10C0h+var_1044]
0x18005673d  mov     [rsp+10C0h+dwFlagsAndAttributes], 0
0x180056745  mov     r8d, 64h ; 'd'
0x18005674b  mov     qword ptr [rsp+10C0h+dwCreationDisposition], rax
0x180056750  lea     r9, [rbp+0FC0h+var_E50]
0x180056757  mov     rdx, r14
0x18005675a  mov     rcx, rdi
0x18005675d  call    cs:__imp_BluetoothGATTGetCharacteristics
0x180056763  mov     ebx, eax
0x180056765  test    eax, eax
0x180056767  js      short loc_180056717
0x180056769  movzx   r15d, [rsp+10C0h+var_1044]
0x18005676f  xor     esi, esi
0x180056771  test    r15d, r15d
0x180056774  jz      short loc_180056712
0x180056776  movsxd  rax, esi
0x180056779  lea     r14, [rax+rax*8]
0x18005677d  cmp     [rbp+r14*4+0FC0h+var_E4C], 0
0x180056786  jnz     short loc_1800567A9
0x180056788  lea     rcx, [rbp+0FC0h+var_E48]
0x18005678f  mov     r8d, 10h; Size
0x180056795  lea     rcx, [rcx+r14*4]; Buf1
0x180056799  lea     rdx, _GUID_7772e5db_3868_4112_a1a9_f2669d106bf3; Buf2
0x1800567a0  call    memcmp_0
0x1800567a5  test    eax, eax
0x1800567a7  jz      short loc_1800567B5
0x1800567a9  inc     esi
0x1800567ab  cmp     esi, r15d
0x1800567ae  jl      short loc_180056776
0x1800567b0  jmp     loc_180056712
0x1800567b5  lea     rsi, [rbp+0FC0h+var_E50]
0x1800567bc  lea     rsi, [rsi+r14*4]
0x1800567c0  test    rsi, rsi
0x1800567c3  jz      loc_180056712
0x1800567c9  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800567ce  mov     r8, rax
0x1800567d1  mov     ecx, [rax]
0x1800567d3  cmp     ecx, 4
0x1800567d6  jbe     loc_180056894
0x1800567dc  mov     al, [rsi+1Eh]
0x1800567df  lea     rdx, byte_180077107
0x1800567e6  mov     cl, [rsi+22h]
0x1800567e9  mov     [rsp+10C0h+var_104C], al
0x1800567ed  mov     al, [rsi+1Dh]
0x1800567f0  mov     [rsp+10C0h+var_104B], al
0x1800567f4  mov     al, [rsi+1Ch]
0x1800567f7  mov     [rsp+10C0h+var_104A], al
0x1800567fb  movzx   eax, word ptr [rsi+1Ah]
0x1800567ff  mov     [rbp+0FC0h+var_1040], ax
0x180056803  movzx   eax, word ptr [rsi+18h]
0x180056807  mov     [rbp+0FC0h+var_103E], ax
0x18005680b  movzx   eax, word ptr [rsi]
0x18005680e  mov     word ptr [rbp+0FC0h+var_103C], ax
0x180056812  lea     rax, [rsp+10C0h+var_1050]
0x180056817  mov     [rsp+10C0h+var_1058], rax
0x18005681c  lea     rax, [rsp+10C0h+var_104F]
0x180056821  mov     [rsp+10C0h+var_1060], rax
0x180056826  lea     rax, [rsp+10C0h+var_104E]
0x18005682b  mov     [rsp+10C0h+var_1068], rax
0x180056830  lea     rax, [rsp+10C0h+var_104D]
0x180056835  mov     [rsp+10C0h+var_1070], rax
0x18005683a  lea     rax, [rsp+10C0h+var_104C]
0x18005683f  mov     [rsp+10C0h+var_1078], rax
0x180056844  lea     rax, [rsp+10C0h+var_104B]
0x180056849  mov     [rsp+10C0h+var_1080], rax
0x18005684e  lea     rax, [rsp+10C0h+var_104A]
0x180056853  mov     [rsp+10C0h+var_1088], rax
0x180056858  lea     rax, [rbp+0FC0h+var_1040]
0x18005685c  mov     [rsp+10C0h+var_1050], cl
0x180056860  mov     cl, [rsi+21h]
0x180056863  mov     [rsp+10C0h+hTemplateFile], rax
0x180056868  lea     rax, [rbp+0FC0h+var_103E]
0x18005686c  mov     [rsp+10C0h+var_104F], cl
0x180056870  mov     cl, [rsi+20h]
0x180056873  mov     [rsp+10C0h+var_104E], cl
0x180056877  mov     cl, [rsi+1Fh]
0x18005687a  mov     qword ptr [rsp+10C0h+dwFlagsAndAttributes], rax
0x18005687f  lea     rax, [rbp+0FC0h+var_103C]
0x180056883  mov     [rsp+10C0h+var_104D], cl
0x180056887  mov     rcx, r8
0x18005688a  mov     qword ptr [rsp+10C0h+dwCreationDisposition], rax
0x18005688f  call    ??$Write@U?$_tlgWrapperByVal@$01@@U1@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@33AEBU?$_tlgWrapperByVal@$00@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x180056894  mov     al, [rsi+1Dh]
0x180056897  mov     [r13+0], al
0x18005689b  mov     al, [rsi+1Fh]
0x18005689e  mov     [r12], al
0x1800568a2  jmp     loc_180056717
0x1800568a7  mov     ebx, 80004003h
0x1800568ac  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800568b1  mov     ecx, [rax]
0x1800568b3  cmp     ecx, 4
0x1800568b6  jbe     short loc_1800568D3
0x1800568b8  lea     rcx, [rbp+0FC0h+var_103C]
0x1800568bc  mov     [rbp+0FC0h+var_103C], ebx
0x1800568bf  mov     qword ptr [rsp+10C0h+dwCreationDisposition], rcx
0x1800568c4  lea     rdx, word_1800770BE
0x1800568cb  mov     rcx, rax
0x1800568ce  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800568d3  mov     eax, ebx
0x1800568d5  mov     rcx, [rbp+0FC0h+var_40]
0x1800568dc  xor     rcx, rsp; StackCookie
0x1800568df  call    __security_check_cookie
0x1800568e4  mov     rbx, [rsp+10C0h+arg_18]
0x1800568ec  add     rsp, 1090h
0x1800568f3  pop     r15
0x1800568f5  pop     r14
0x1800568f7  pop     r13
0x1800568f9  pop     r12
0x1800568fb  pop     rdi
0x1800568fc  pop     rsi
0x1800568fd  pop     rbp
0x1800568fe  retn
```
