# CMsmqVssWriter::AddServiceConfig(IVssCreateWriterMetadata *,wchar_t const *)

- ea: `0x18008dd84`
- end: `0x18008e269`
- name: `?AddServiceConfig@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@PEB_W@Z`
- size: `1253`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, struct IVssCreateWriterMetadata *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008dbe0`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008dd84`
- `0x18008e270`
- `0x18009aa2c`
- `0x18009bd1c`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x18008deb6`
- `msvcrt!free` at `0x18008df1c`
- `msvcrt!free` at `0x18008df89`
- `msvcrt!free` at `0x18008dfed`
- `msvcrt!free` at `0x18008e0c4`
- `msvcrt!free` at `0x18008e128`
- `msvcrt!free` at `0x18008e18c`
- `msvcrt!free` at `0x18008e196`
- `msvcrt!free` at `0x18008e1e3`
- `msvcrt!free` at `0x18008e1ed`
- `msvcrt!free` at `0x18008e222`
- `msvcrt!free` at `0x18008e22c`
- `msvcrt!free` at `0x18008e23a`
- `msvcrt!free` at `0x18008e244`
- `msvcrt!free` at `0x18008deb6`
- `msvcrt!free` at `0x18008df1c`
- `msvcrt!free` at `0x18008df89`
- `msvcrt!free` at `0x18008dfed`
- `msvcrt!free` at `0x18008e0c4`
- `msvcrt!free` at `0x18008e128`
- `msvcrt!free` at `0x18008e18c`
- `msvcrt!free` at `0x18008e196`
- `msvcrt!free` at `0x18008e1e3`
- `msvcrt!free` at `0x18008e1ed`
- `msvcrt!free` at `0x18008e222`
- `msvcrt!free` at `0x18008e22c`
- `msvcrt!free` at `0x18008e23a`
- `msvcrt!free` at `0x18008e244`

## string_xrefs

- `0x18008ddfe`: `writer/mqwriter`
- `0x18008dea4`: `writer/mqwriter`
- `0x18008df0a`: `writer/mqwriter`
- `0x18008df77`: `writer/mqwriter`
- `0x18008dfdb`: `writer/mqwriter`
- `0x18008e0b2`: `writer/mqwriter`
- `0x18008e116`: `writer/mqwriter`
- `0x18008e17a`: `writer/mqwriter`
- `0x18008e1d1`: `writer/mqwriter`
- `0x18008e210`: `writer/mqwriter`
- `0x18008ddd4`: `config`
- `0x18008e0e5`: `msmqwebacl.bkp`
- `0x18008df50`: `registry`
- `0x18008dfb9`: `registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMsmqVssWriter::AddServiceConfig(
        CMsmqVssWriter *this,
        struct IVssCreateWriterMetadata *a2,
        const wchar_t *a3)
{
  int v6; // ebx
  unsigned __int16 v7; // r8
  wchar_t *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  wchar_t *v15; // rdi
  int v16; // eax
  unsigned int v17; // ebp
  int v18; // eax
  int v19; // eax
  unsigned int v20; // esi
  int v21; // [rsp+28h] [rbp-A0h]
  int v22; // [rsp+28h] [rbp-A0h]
  char v23; // [rsp+38h] [rbp-90h]
  int v24; // [rsp+38h] [rbp-90h]
  int v25; // [rsp+38h] [rbp-90h]
  char v26; // [rsp+40h] [rbp-88h]
  int v27; // [rsp+40h] [rbp-88h]
  int v28; // [rsp+40h] [rbp-88h]
  char v29; // [rsp+48h] [rbp-80h]
  int v30; // [rsp+48h] [rbp-80h]
  int v31; // [rsp+48h] [rbp-80h]
  char v32; // [rsp+50h] [rbp-78h]
  int v33; // [rsp+50h] [rbp-78h]
  int v34; // [rsp+50h] [rbp-78h]
  int v35; // [rsp+78h] [rbp-50h] BYREF
  const wchar_t *v36; // [rsp+80h] [rbp-48h]
  const wchar_t *v37; // [rsp+88h] [rbp-40h]
  int v38; // [rsp+90h] [rbp-38h]
  __int64 v39; // [rsp+98h] [rbp-30h]

  v32 = 1;
  v29 = 1;
  v26 = 0;
  v23 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         0,
         L"config",
         0,
         0,
         0,
         v23,
         v26,
         v29,
         v32,
         0);
  if ( v6 < 0 )
  {
    v7 = 720;
LABEL_3:
    LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", v7);
    return (unsigned int)v6;
  }
  LOBYTE(v33) = 1;
  LOBYTE(v30) = 1;
  LOBYTE(v27) = 0;
  LOBYTE(v24) = 0;
  v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, _DWORD, int, int, int, int, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         L"config",
         L"sysq",
         0,
         0,
         0,
         v24,
         v27,
         v30,
         v33,
         0);
  if ( v6 < 0 )
  {
    v7 = 730;
    goto LABEL_3;
  }
  v9 = (wchar_t *)MmAllocate(0x20Au);
  v10 = StringCchPrintfW(v9, 0x105u, L"%s\\%s", a3, L"config");
  v11 = v10;
  if ( v10 < 0 )
  {
    LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0x2E4u);
    free(v9);
    return v11;
  }
  LOBYTE(v21) = 0;
  v12 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, const wchar_t *, const wchar_t *, wchar_t *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
          a2,
          L"config",
          L"sysq",
          v9,
          L"0*.*",
          v21,
          0,
          3855);
  v11 = v12;
  if ( v12 < 0 )
  {
    LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0x2F8u);
    free(v9);
    return v11;
  }
  LOBYTE(v34) = 1;
  LOBYTE(v31) = 1;
  LOBYTE(v28) = 0;
  LOBYTE(v25) = 0;
  v13 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, _DWORD, int, int, int, int, _DWORD))(*(_QWORD *)a2 + 16LL))(
          a2,
          2,
          L"config",
          L"registry",
          0,
          0,
          0,
          v25,
          v28,
          v31,
          v34,
          0);
  v11 = v13;
  if ( v13 < 0 )
  {
    LogMsgHR(v13, (wchar_t *)L"writer/mqwriter", 0x302u);
    free(v9);
    return v11;
  }
  LOBYTE(v22) = 0;
  v14 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, const wchar_t *, const wchar_t *, wchar_t *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
          a2,
          L"config",
          L"registry",
          v9,
          L"msmqreg.bkp",
          v22,
          0,
          3855);
  v11 = v14;
  if ( v14 < 0 )
  {
    LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x30Cu);
    free(v9);
    return v11;
  }
  v35 = 0;
  v36 = L"SOFTWARE\\Microsoft\\MSMQ\\Setup";
  v37 = L"msmq_HTTPSupport";
  v38 = 0;
  v39 = -2147483646;
  QueryValueInternal((struct RegEntry *)&v35);
  v15 = (wchar_t *)MmAllocate(0x20Au);
  v16 = StringCchPrintfW(v15, 0x105u, L"%s\\%s\\%s", a3, L"Restore", L"config");
  v17 = v16;
  if ( v16 < 0 )
  {
    LogMsgHR(v16, (wchar_t *)L"writer/mqwriter", 0x322u);
    free(v15);
    free(v9);
    return v17;
  }
  v18 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, wchar_t *, const wchar_t *, _QWORD, wchar_t *))(*(_QWORD *)a2 + 56LL))(
          a2,
          v9,
          L"*",
          0,
          v15);
  v17 = v18;
  if ( v18 < 0 )
  {
    LogMsgHR(v18, (wchar_t *)L"writer/mqwriter", 0x324u);
    free(v15);
    free(v9);
    return v17;
  }
  v19 = CMsmqVssWriter::AddServiceMapping(this, a2, a3);
  v20 = v19;
  if ( v19 >= 0 )
  {
    free(v15);
    free(v9);
    return 0;
  }
  else
  {
    LogMsgHR(v19, (wchar_t *)L"writer/mqwriter", 0x33Eu);
    free(v15);
    free(v9);
    return v20;
  }
}

```

## disassembly

```asm
0x18008dd84  mov     [rsp+arg_0], rbx
0x18008dd89  mov     [rsp+arg_10], rbp
0x18008dd8e  push    rsi
0x18008dd8f  push    rdi
0x18008dd90  push    r12
0x18008dd92  push    r14
0x18008dd94  push    r15
0x18008dd96  sub     rsp, 0A0h
0x18008dd9d  mov     r14, r8
0x18008dda0  mov     rsi, rdx
0x18008dda3  mov     r15, rcx
0x18008dda6  mov     rax, [rdx]
0x18008dda9  xor     r12d, r12d
0x18008ddac  mov     [rsp+0C8h+var_70], r12d
0x18008ddb1  mov     [rsp+0C8h+var_78], 1
0x18008ddb6  mov     [rsp+0C8h+var_80], 1
0x18008ddbb  mov     [rsp+0C8h+var_88], r12b
0x18008ddc0  mov     byte ptr [rsp+0C8h+var_90], r12b
0x18008ddc5  mov     dword ptr [rsp+0C8h+var_98], r12d
0x18008ddca  mov     [rsp+0C8h+var_A0], r12
0x18008ddcf  mov     [rsp+0C8h+var_A8], r12
0x18008ddd4  lea     rbp, aConfig; "config"
0x18008dddb  mov     r9, rbp
0x18008ddde  xor     r8d, r8d
0x18008dde1  lea     edx, [r12+2]
0x18008dde6  mov     rcx, rsi
0x18008dde9  mov     rax, [rax+10h]
0x18008dded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ddf2  mov     ebx, eax
0x18008ddf4  test    eax, eax
0x18008ddf6  jns     short loc_18008DE13
0x18008ddf8  mov     r8d, 2D0h; unsigned __int16
0x18008ddfe  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008de05  mov     ecx, ebx; int
0x18008de07  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008de0c  mov     eax, ebx
0x18008de0e  jmp     loc_18008E24D
0x18008de13  mov     rax, [rsi]
0x18008de16  mov     [rsp+0C8h+var_70], r12d
0x18008de1b  mov     [rsp+0C8h+var_78], 1
0x18008de20  mov     [rsp+0C8h+var_80], 1
0x18008de25  mov     [rsp+0C8h+var_88], r12b
0x18008de2a  mov     byte ptr [rsp+0C8h+var_90], r12b
0x18008de2f  mov     dword ptr [rsp+0C8h+var_98], r12d
0x18008de34  mov     [rsp+0C8h+var_A0], r12
0x18008de39  mov     [rsp+0C8h+var_A8], r12
0x18008de3e  lea     r9, aSysq; "sysq"
0x18008de45  mov     r8, rbp
0x18008de48  mov     edx, 2
0x18008de4d  mov     rcx, rsi
0x18008de50  mov     rax, [rax+10h]
0x18008de54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de59  mov     ebx, eax
0x18008de5b  test    eax, eax
0x18008de5d  jns     short loc_18008DE67
0x18008de5f  mov     r8d, 2DAh
0x18008de65  jmp     short loc_18008DDFE
0x18008de67  mov     ecx, 20Ah; unsigned __int64
0x18008de6c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008de71  mov     rbx, rax
0x18008de74  mov     [rsp+0C8h+arg_18], rax
0x18008de7c  mov     [rsp+0C8h+var_A8], rbp
0x18008de81  mov     r9, r14
0x18008de84  lea     r8, aSS_3; "%s\\%s"
0x18008de8b  mov     edx, 105h; unsigned __int64
0x18008de90  mov     rcx, rax; wchar_t *
0x18008de93  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008de98  mov     edi, eax
0x18008de9a  test    eax, eax
0x18008de9c  jns     short loc_18008DEC4
0x18008de9e  mov     r8d, 2E4h; unsigned __int16
0x18008dea4  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008deab  mov     ecx, eax; int
0x18008dead  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008deb2  nop
0x18008deb3  mov     rcx, rbx; Block
0x18008deb6  call    cs:__imp_free
0x18008debc  nop
0x18008debd  mov     eax, edi
0x18008debf  jmp     loc_18008E24D
0x18008dec4  mov     rax, [rsi]
0x18008dec7  mov     [rsp+0C8h+var_90], 0F0Fh
0x18008decf  mov     [rsp+0C8h+var_98], r12
0x18008ded4  mov     byte ptr [rsp+0C8h+var_A0], r12b
0x18008ded9  lea     rcx, a0; "0*.*"
0x18008dee0  mov     [rsp+0C8h+var_A8], rcx
0x18008dee5  mov     r9, rbx
0x18008dee8  lea     r8, aSysq; "sysq"
0x18008deef  mov     rdx, rbp
0x18008def2  mov     rcx, rsi
0x18008def5  mov     rax, [rax+28h]
0x18008def9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008defe  mov     edi, eax
0x18008df00  test    eax, eax
0x18008df02  jns     short loc_18008DF25
0x18008df04  mov     r8d, 2F8h; unsigned __int16
0x18008df0a  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008df11  mov     ecx, eax; int
0x18008df13  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008df18  nop
0x18008df19  mov     rcx, rbx; Block
0x18008df1c  call    cs:__imp_free
0x18008df22  nop
0x18008df23  jmp     short loc_18008DEBD
0x18008df25  mov     rax, [rsi]
0x18008df28  mov     [rsp+0C8h+var_70], r12d
0x18008df2d  mov     [rsp+0C8h+var_78], 1
0x18008df32  mov     [rsp+0C8h+var_80], 1
0x18008df37  mov     [rsp+0C8h+var_88], r12b
0x18008df3c  mov     byte ptr [rsp+0C8h+var_90], r12b
0x18008df41  mov     dword ptr [rsp+0C8h+var_98], r12d
0x18008df46  mov     [rsp+0C8h+var_A0], r12
0x18008df4b  mov     [rsp+0C8h+var_A8], r12
0x18008df50  lea     r9, aRegistry; "registry"
0x18008df57  mov     r8, rbp
0x18008df5a  mov     edx, 2
0x18008df5f  mov     rcx, rsi
0x18008df62  mov     rax, [rax+10h]
0x18008df66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df6b  mov     edi, eax
0x18008df6d  test    eax, eax
0x18008df6f  jns     short loc_18008DF95
0x18008df71  mov     r8d, 302h; unsigned __int16
0x18008df77  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008df7e  mov     ecx, eax; int
0x18008df80  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008df85  nop
0x18008df86  mov     rcx, rbx; Block
0x18008df89  call    cs:__imp_free
0x18008df8f  nop
0x18008df90  jmp     loc_18008DEBD
0x18008df95  mov     rax, [rsi]
0x18008df98  mov     [rsp+0C8h+var_90], 0F0Fh
0x18008dfa0  mov     [rsp+0C8h+var_98], r12
0x18008dfa5  mov     byte ptr [rsp+0C8h+var_A0], r12b
0x18008dfaa  lea     rcx, aMsmqregBkp; "msmqreg.bkp"
0x18008dfb1  mov     [rsp+0C8h+var_A8], rcx
0x18008dfb6  mov     r9, rbx
0x18008dfb9  lea     r8, aRegistry; "registry"
0x18008dfc0  mov     rdx, rbp
0x18008dfc3  mov     rcx, rsi
0x18008dfc6  mov     rax, [rax+28h]
0x18008dfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dfcf  mov     edi, eax
0x18008dfd1  test    eax, eax
0x18008dfd3  jns     short loc_18008DFF9
0x18008dfd5  mov     r8d, 30Ch; unsigned __int16
0x18008dfdb  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008dfe2  mov     ecx, eax; int
0x18008dfe4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008dfe9  nop
0x18008dfea  mov     rcx, rbx; Block
0x18008dfed  call    cs:__imp_free
0x18008dff3  nop
0x18008dff4  jmp     loc_18008DEBD
0x18008dff9  mov     [rsp+0C8h+var_50], r12d
0x18008dffe  lea     rax, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\MSMQ\\Setup"
0x18008e005  mov     [rsp+0C8h+var_48], rax
0x18008e00d  lea     rax, aMsmqHttpsuppor; "msmq_HTTPSupport"
0x18008e014  mov     [rsp+0C8h+var_40], rax
0x18008e01c  mov     [rsp+0C8h+var_38], r12d
0x18008e024  mov     [rsp+0C8h+var_30], 0FFFFFFFF80000002h
0x18008e030  mov     [rsp+0C8h+arg_8], r12d
0x18008e038  mov     edx, 4
0x18008e03d  mov     r9d, edx
0x18008e040  lea     r8, [rsp+0C8h+arg_8]
0x18008e048  lea     rcx, [rsp+0C8h+var_50]; struct RegEntry *
0x18008e04d  call    QueryValueInternal
0x18008e052  cmp     [rsp+0C8h+arg_8], r12d
0x18008e05a  jz      loc_18008E134
0x18008e060  mov     rax, [rsi]
0x18008e063  mov     [rsp+0C8h+var_70], r12d
0x18008e068  mov     [rsp+0C8h+var_78], 1
0x18008e06d  mov     [rsp+0C8h+var_80], 1
0x18008e072  mov     [rsp+0C8h+var_88], r12b
0x18008e077  mov     byte ptr [rsp+0C8h+var_90], r12b
0x18008e07c  mov     dword ptr [rsp+0C8h+var_98], r12d
0x18008e081  mov     [rsp+0C8h+var_A0], r12
0x18008e086  mov     [rsp+0C8h+var_A8], r12
0x18008e08b  lea     r9, aHttps_0; "https"
0x18008e092  mov     r8, rbp
0x18008e095  mov     edx, 2
0x18008e09a  mov     rcx, rsi
0x18008e09d  mov     rax, [rax+10h]
0x18008e0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e0a6  mov     edi, eax
0x18008e0a8  test    eax, eax
0x18008e0aa  jns     short loc_18008E0D0
0x18008e0ac  mov     r8d, 316h; unsigned __int16
0x18008e0b2  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e0b9  mov     ecx, eax; int
0x18008e0bb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e0c0  nop
0x18008e0c1  mov     rcx, rbx; Block
0x18008e0c4  call    cs:__imp_free
0x18008e0ca  nop
0x18008e0cb  jmp     loc_18008DEBD
0x18008e0d0  mov     rax, [rsi]
0x18008e0d3  mov     [rsp+0C8h+var_90], 0F0Fh
0x18008e0db  mov     [rsp+0C8h+var_98], r12
0x18008e0e0  mov     byte ptr [rsp+0C8h+var_A0], r12b
0x18008e0e5  lea     rcx, aMsmqwebaclBkp; "msmqwebacl.bkp"
0x18008e0ec  mov     [rsp+0C8h+var_A8], rcx
0x18008e0f1  mov     r9, rbx
0x18008e0f4  lea     r8, aHttps_0; "https"
0x18008e0fb  mov     rdx, rbp
0x18008e0fe  mov     rcx, rsi
0x18008e101  mov     rax, [rax+28h]
0x18008e105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e10a  mov     edi, eax
0x18008e10c  test    eax, eax
0x18008e10e  jns     short loc_18008E134
0x18008e110  mov     r8d, 320h; unsigned __int16
0x18008e116  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e11d  mov     ecx, eax; int
0x18008e11f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e124  nop
0x18008e125  mov     rcx, rbx; Block
0x18008e128  call    cs:__imp_free
0x18008e12e  nop
0x18008e12f  jmp     loc_18008DEBD
0x18008e134  mov     ecx, 20Ah; unsigned __int64
0x18008e139  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008e13e  mov     rdi, rax
0x18008e141  mov     [rsp+0C8h+var_58], rax
0x18008e146  mov     [rsp+0C8h+var_A0], rbp
0x18008e14b  lea     rax, aRestore; "Restore"
0x18008e152  mov     [rsp+0C8h+var_A8], rax
0x18008e157  mov     r9, r14
0x18008e15a  lea     r8, aSSS; "%s\\%s\\%s"
0x18008e161  mov     edx, 105h; unsigned __int64
0x18008e166  mov     rcx, rdi; wchar_t *
0x18008e169  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008e16e  mov     ebp, eax
0x18008e170  test    eax, eax
0x18008e172  jns     short loc_18008E1A4
0x18008e174  mov     r8d, 322h; unsigned __int16
0x18008e17a  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e181  mov     ecx, eax; int
0x18008e183  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e188  nop
0x18008e189  mov     rcx, rdi; Block
0x18008e18c  call    cs:__imp_free
0x18008e192  nop
0x18008e193  mov     rcx, rbx; Block
0x18008e196  call    cs:__imp_free
0x18008e19c  nop
0x18008e19d  mov     eax, ebp
0x18008e19f  jmp     loc_18008E24D
0x18008e1a4  mov     rax, [rsi]
0x18008e1a7  mov     [rsp+0C8h+var_A8], rdi
0x18008e1ac  xor     r9d, r9d
0x18008e1af  lea     r8, asc_180104F98; "*"
0x18008e1b6  mov     rdx, rbx
0x18008e1b9  mov     rcx, rsi
0x18008e1bc  mov     rax, [rax+38h]
0x18008e1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1c5  mov     ebp, eax
0x18008e1c7  test    eax, eax
0x18008e1c9  jns     short loc_18008E1F6
0x18008e1cb  mov     r8d, 324h; unsigned __int16
0x18008e1d1  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e1d8  mov     ecx, eax; int
0x18008e1da  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e1df  nop
0x18008e1e0  mov     rcx, rdi; Block
0x18008e1e3  call    cs:__imp_free
0x18008e1e9  nop
0x18008e1ea  mov     rcx, rbx; Block
0x18008e1ed  call    cs:__imp_free
0x18008e1f3  nop
0x18008e1f4  jmp     short loc_18008E19D
0x18008e1f6  mov     r8, r14; wchar_t *
0x18008e1f9  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18008e1fc  mov     rcx, r15; this
0x18008e1ff  call    ?AddServiceMapping@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@PEB_W@Z; CMsmqVssWriter::AddServiceMapping(IVssCreateWriterMetadata *,wchar_t const *)
0x18008e204  mov     esi, eax
0x18008e206  test    eax, eax
0x18008e208  jns     short loc_18008E237
0x18008e20a  mov     r8d, 33Eh; unsigned __int16
0x18008e210  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e217  mov     ecx, eax; int
0x18008e219  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e21e  nop
0x18008e21f  mov     rcx, rdi; Block
0x18008e222  call    cs:__imp_free
0x18008e228  nop
0x18008e229  mov     rcx, rbx; Block
0x18008e22c  call    cs:__imp_free
0x18008e232  nop
0x18008e233  mov     eax, esi
0x18008e235  jmp     short loc_18008E24D
0x18008e237  mov     rcx, rdi; Block
0x18008e23a  call    cs:__imp_free
0x18008e240  nop
0x18008e241  mov     rcx, rbx; Block
0x18008e244  call    cs:__imp_free
0x18008e24a  nop
0x18008e24b  xor     eax, eax
0x18008e24d  lea     r11, [rsp+0C8h+var_28]
  ... truncated ...
```
