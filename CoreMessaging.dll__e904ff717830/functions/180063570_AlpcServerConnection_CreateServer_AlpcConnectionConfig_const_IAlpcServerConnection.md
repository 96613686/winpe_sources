# AlpcServerConnection::CreateServer(AlpcConnectionConfig const *,IAlpcServerConnection * *)

- ea: `0x180063570`
- end: `0x180063732`
- name: `?CreateServer@AlpcServerConnection@@SAJPEBUAlpcConnectionConfig@@PEAPEAUIAlpcServerConnection@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(const struct AlpcConnectionConfig *, struct IAlpcServerConnection **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800922cc`
- `0x1800b9390`

## callees

- `0x180063570`
- `0x180063934`
- `0x180063970`
- `0x18009d670`
- `0x18009e054`
- `0x1800a1f68`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063718`
- `ntdll!NtAlpcCreatePort` at `0x1800636b4`
- `ntdll!NtAlpcCreatePort` at `0x1800636b4`
- `ntdll!RtlInitUnicodeString` at `0x18006369a`
- `ntdll!RtlInitUnicodeString` at `0x18006369a`

## pseudocode

```c
__int64 __fastcall AlpcServerConnection::CreateServer(
        const struct AlpcConnectionConfig *a1,
        struct IAlpcServerConnection **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rbx
  const WCHAR *v7; // rdx
  int v8; // eax
  int v9; // ebx
  unsigned __int64 v10; // rcx
  __int128 v12; // [rsp+20h] [rbp-69h] BYREF
  __int128 v13; // [rsp+30h] [rbp-59h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-49h]
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-39h] BYREF
  _DWORD v16[3]; // [rsp+60h] [rbp-29h] BYREF
  __int16 v17; // [rsp+6Ch] [rbp-1Dh]
  __int64 v18; // [rsp+70h] [rbp-19h]

  v4 = AlpcConnection::operator new(0xB8u);
  *(_QWORD *)&DestinationString.Length = v4;
  v5 = v4;
  if ( !v4 )
    Cn::Process::NotifyOutOfMemory(0);
  memset_0(v4, 0, 0xB8u);
  v5[4] = 0;
  v5[5] = 0;
  v5[6] = 0;
  *v5 = &AlpcServerConnection::`vftable'{for `AlpcConnection'};
  v5[12] = &AlpcServerConnection::`vftable'{for `IAlpcServerConnection'};
  *((_DWORD *)v5 + 4) = 1;
  v5[13] = v5 + 15;
  *((_DWORD *)v5 + 29) = 8;
  *((_DWORD *)v5 + 28) = 0;
  *((_BYTE *)v5 + 58) |= 1u;
  v12 = 0;
  v13 = 0;
  *(_OWORD *)hMem = 0;
  memset_0(v16, 0, 0x48u);
  AlpcConnection::InitializeFromSettings((AlpcConnection *)v5, a1);
  v6 = *((unsigned __int16 *)v5 + 36);
  v12 = 0x30u;
  *((_QWORD *)&v13 + 1) = 0;
  memset_0(v16, 0, 0x48u);
  v7 = *(const WCHAR **)a1;
  hMem[0] = *((HLOCAL *)a1 + 2);
  DestinationString = 0;
  hMem[1] = 0;
  v16[0] = 458752;
  v18 = v6;
  v16[1] = 12;
  v16[2] = 1;
  v17 = 256;
  RtlInitUnicodeString(&DestinationString, v7);
  *(_QWORD *)&v13 = &DestinationString;
  v8 = NtAlpcCreatePort(v5 + 3, &v12, v16) | 0x10000000;
  v9 = 0;
  if ( v8 < 0 )
    v9 = v8;
  if ( hMem[0] != *((HLOCAL *)a1 + 2) && hMem[0] )
  {
    LocalFree(hMem[0]);
    hMem[0] = 0;
  }
  v10 = (unsigned __int64)(v5 + 12);
  if ( v9 < 0 )
  {
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 8LL))(v10);
  }
  else
  {
    v9 = 0;
    *a2 = (struct IAlpcServerConnection *)(v10 & -(__int64)(v5 != 0));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180063570  mov     [rsp-8+arg_10], rbx
0x180063575  push    rbp
0x180063576  push    rsi
0x180063577  push    rdi
0x180063578  push    r12
0x18006357a  push    r14
0x18006357c  lea     rbp, [rsp-37h]
0x180063581  sub     rsp, 0C0h
0x180063588  mov     rax, cs:__security_cookie
0x18006358f  xor     rax, rsp
0x180063592  mov     [rbp+57h+var_30], rax
0x180063596  mov     r14, rcx
0x180063599  mov     ebx, 0B8h
0x18006359e  mov     ecx, ebx; Size
0x1800635a0  mov     rsi, rdx
0x1800635a3  call    ??2AlpcConnection@@KAPEAX_K@Z; AlpcConnection::operator new(unsigned __int64)
0x1800635a8  xor     r12d, r12d
0x1800635ab  mov     qword ptr [rbp+57h+DestinationString.Length], rax
0x1800635af  mov     rdi, rax
0x1800635b2  test    rax, rax
0x1800635b5  jz      loc_18006370B
0x1800635bb  mov     r8d, ebx; Size
0x1800635be  xor     edx, edx; Val
0x1800635c0  mov     rcx, rax; void *
0x1800635c3  call    memset_0
0x1800635c8  mov     [rdi+20h], r12
0x1800635cc  lea     rax, ??_7AlpcServerConnection@@6BAlpcConnection@@@; const AlpcServerConnection::`vftable'{for `AlpcConnection'}
0x1800635d3  mov     [rdi+28h], r12
0x1800635d7  mov     [rdi+30h], r12
0x1800635db  mov     [rdi], rax
0x1800635de  lea     rax, ??_7AlpcServerConnection@@6BIAlpcServerConnection@@@; const AlpcServerConnection::`vftable'{for `IAlpcServerConnection'}
0x1800635e5  mov     [rdi+60h], rax
0x1800635e9  lea     rax, [rdi+78h]
0x1800635ed  mov     dword ptr [rdi+10h], 1
0x1800635f4  mov     [rdi+68h], rax
0x1800635f8  mov     dword ptr [rdi+74h], 8
0x1800635ff  mov     [rdi+70h], r12d
0x180063603  test    rdi, rdi
0x180063606  jz      loc_18006370B
0x18006360c  or      byte ptr [rdi+3Ah], 1
0x180063610  lea     r8d, [rbx-70h]; Size
0x180063614  xorps   xmm0, xmm0
0x180063617  lea     rcx, [rbp+57h+var_80]; void *
0x18006361b  xor     edx, edx; Val
0x18006361d  movups  [rbp+57h+var_C0], xmm0
0x180063621  movups  [rbp+57h+var_B0], xmm0
0x180063625  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180063629  call    memset_0
0x18006362e  mov     rdx, r14; struct AlpcConnectionConfig *
0x180063631  mov     rcx, rdi; this
0x180063634  call    ?InitializeFromSettings@AlpcConnection@@IEAAXPEBUAlpcConnectionConfig@@@Z; AlpcConnection::InitializeFromSettings(AlpcConnectionConfig const *)
0x180063639  movzx   ebx, word ptr [rdi+48h]
0x18006363d  lea     r8d, [r12+48h]; Size
0x180063642  xor     edx, edx; Val
0x180063644  mov     qword ptr [rbp+57h+var_C0], 30h ; '0'
0x18006364c  lea     rcx, [rbp+57h+var_80]; void *
0x180063650  mov     qword ptr [rbp+57h+var_B0+8], r12
0x180063654  call    memset_0
0x180063659  mov     rax, [r14+10h]
0x18006365d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180063661  mov     rdx, [r14]; SourceString
0x180063664  xorps   xmm0, xmm0
0x180063667  mov     [rbp+57h+hMem], rax
0x18006366b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006366f  mov     qword ptr [rbp+57h+var_C0+8], r12
0x180063673  mov     qword ptr [rbp+57h+var_B0], r12
0x180063677  mov     [rbp+57h+hMem+8], r12
0x18006367b  mov     [rbp+57h+var_80], 70000h
0x180063682  mov     [rbp+57h+var_70], rbx
0x180063686  mov     [rbp+57h+var_7C], 0Ch
0x18006368d  mov     [rbp+57h+var_78], 1
0x180063694  mov     [rbp+57h+var_74], 100h
0x18006369a  call    cs:__imp_RtlInitUnicodeString
0x1800636a0  lea     rax, [rbp+57h+DestinationString]
0x1800636a4  lea     rcx, [rdi+18h]
0x1800636a8  mov     qword ptr [rbp+57h+var_B0], rax
0x1800636ac  lea     r8, [rbp+57h+var_80]
0x1800636b0  lea     rdx, [rbp+57h+var_C0]
0x1800636b4  call    cs:__imp_NtAlpcCreatePort
0x1800636ba  or      eax, 10000000h
0x1800636bf  mov     rcx, [rbp+57h+hMem]; hMem
0x1800636c3  mov     ebx, r12d
0x1800636c6  cmovl   ebx, eax
0x1800636c9  cmp     rcx, [r14+10h]
0x1800636cd  jnz     short loc_180063713
0x1800636cf  lea     rcx, [rdi+60h]
0x1800636d3  test    ebx, ebx
0x1800636d5  js      short loc_180063724
0x1800636d7  neg     rdi
0x1800636da  mov     ebx, r12d
0x1800636dd  sbb     rax, rax
0x1800636e0  and     rax, rcx
0x1800636e3  mov     [rsi], rax
0x1800636e6  mov     eax, ebx
0x1800636e8  mov     rcx, [rbp+57h+var_30]
0x1800636ec  xor     rcx, rsp; StackCookie
0x1800636ef  call    __security_check_cookie
0x1800636f4  mov     rbx, [rsp+0E0h+arg_10]
0x1800636fc  add     rsp, 0C0h
0x180063703  pop     r14
0x180063705  pop     r12
0x180063707  pop     rdi
0x180063708  pop     rsi
0x180063709  pop     rbp
0x18006370a  retn
0x18006370b  xor     ecx, ecx; unsigned __int64
0x18006370d  call    ?NotifyOutOfMemory@Process@Cn@@SAX_K@Z; Cn::Process::NotifyOutOfMemory(unsigned __int64)
0x180063713  test    rcx, rcx
0x180063716  jz      short loc_1800636CF
0x180063718  call    cs:__imp_LocalFree
0x18006371e  mov     [rbp+57h+hMem], r12
0x180063722  jmp     short loc_1800636CF
0x180063724  mov     rdx, [rcx]
0x180063727  mov     rax, [rdx+8]
0x18006372b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063730  jmp     short loc_1800636E6
```
