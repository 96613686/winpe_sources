# CNTService::CNTService(ushort const *,ushort const *,ushort const *)

- ea: `0x14000445c`
- end: `0x140004727`
- name: `??0CNTService@@QEAA@PEBG00@Z`
- size: `715`
- prototype: `CNTService *__fastcall(CNTService *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140003218`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x14000445c`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400044f8`
- `KERNEL32!IsDebuggerPresent` at `0x1400045b1`
- `KERNEL32!IsDebuggerPresent` at `0x140004665`
- `KERNEL32!IsDebuggerPresent` at `0x1400044f8`
- `KERNEL32!IsDebuggerPresent` at `0x1400045b1`
- `KERNEL32!IsDebuggerPresent` at `0x140004665`

## string_xrefs

- `0x140004558`: `@:Windows MultiPoint Server Self-Healing Service`
- `0x140004484`: `WmsRepair`
- `0x1400044d0`: `CNTService::CNTService`
- `0x1400044d7`: `termsrv\wms\src\common\ntservice\ntservice.cpp`

## pseudocode

```c
CNTService *__fastcall CNTService::CNTService(
        CNTService *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rsi
  const wchar_t *v6; // r8
  __int64 v7; // rdi
  __int64 v8; // rcx
  _WORD *v9; // rax
  __int64 v10; // rdx
  _WORD *v11; // rcx
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  _WORD *v14; // rax
  _WORD *v15; // rcx
  const wchar_t *v16; // rcx
  __int64 v17; // rdx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  CNTService *result; // rax
  __int128 v21; // xmm0
  __int128 v22; // xmm1

  CNTService::s_pSingleInstance = this;
  v5 = 2147483646;
  *(_QWORD *)this = &CNTService::`vftable';
  v6 = L"WmsRepair";
  v7 = 64;
  v8 = 2147483646;
  v9 = (_WORD *)((char *)this + 8);
  v10 = 64;
  do
  {
    if ( !v8 )
      break;
    a4 = (const unsigned __int16 *)*v6;
    if ( !(_WORD)a4 )
      break;
    *v9 = (_WORD)a4;
    ++v6;
    ++v9;
    --v8;
    --v10;
  }
  while ( v10 );
  v11 = v9 - 1;
  if ( v10 )
    v11 = v9;
  *v11 = 0;
  if ( !v10 )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x2Cu,
      L"CNTService::CNTService",
      a4,
      L"SUCCEEDED (hr)");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        44,
        L"CNTService::CNTService",
        L"ASSERT",
        L"SUCCEEDED (hr)");
  }
  v12 = 2147483646;
  v13 = L"@:Windows MultiPoint Server Self-Healing Service";
  v14 = (_WORD *)((char *)this + 136);
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *v14++ = *v13++;
    --v12;
    --v7;
  }
  while ( v7 );
  v15 = v14 - 1;
  if ( v7 )
    v15 = v14;
  *v15 = 0;
  if ( !v7 )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x30u,
      L"CNTService::CNTService",
      a4,
      L"SUCCEEDED (hr)");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        48,
        L"CNTService::CNTService",
        L"ASSERT",
        L"SUCCEEDED (hr)");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        48,
        L"CNTService::CNTService",
        L"ASSERT",
        L"SUCCEEDED (hr)");
  }
  v16 = L"@:Provides self-healing for Windows MultiPoint Server.";
  v17 = 256;
  v18 = (_WORD *)((char *)this + 264);
  do
  {
    if ( !v5 )
      break;
    if ( !*v16 )
      break;
    *v18++ = *v16++;
    --v5;
    --v17;
  }
  while ( v17 );
  v19 = v18 - 1;
  if ( v17 )
    v19 = v18;
  *v19 = 0;
  if ( !v17 )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x34u,
      L"CNTService::CNTService",
      a4,
      L"SUCCEEDED (hr)");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        52,
        L"CNTService::CNTService",
        L"ASSERT",
        L"SUCCEEDED (hr)");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        52,
        L"CNTService::CNTService",
        L"ASSERT",
        L"SUCCEEDED (hr)");
  }
  *((_DWORD *)this + 196) = 16;
  result = this;
  *((_DWORD *)this + 197) = 1;
  *((_QWORD *)this + 99) = 741;
  *((_QWORD *)this + 100) = 0;
  *((_DWORD *)this + 202) = 0;
  v21 = *((_OWORD *)this + 49);
  *((_QWORD *)this + 97) = 0;
  v22 = *(_OWORD *)((char *)this + 796);
  *((_QWORD *)this + 105) = -1;
  *(_OWORD *)((char *)this + 812) = v21;
  *(_OWORD *)((char *)this + 824) = v22;
  return result;
}

```

## disassembly

```asm
0x14000445c  push    rbx
0x14000445e  push    rbp
0x14000445f  push    rsi
0x140004460  push    rdi
0x140004461  push    r12
0x140004463  push    r13
0x140004465  push    r15
0x140004467  sub     rsp, 40h
0x14000446b  mov     rbx, rcx
0x14000446e  mov     cs:?s_pSingleInstance@CNTService@@2PEAV1@EA, rcx; CNTService * CNTService::s_pSingleInstance
0x140004475  lea     rax, ??_7CNTService@@6B@; const CNTService::`vftable'
0x14000447c  mov     esi, 7FFFFFFEh
0x140004481  mov     [rcx], rax
0x140004484  lea     r8, aWmsrepair; "WmsRepair"
0x14000448b  mov     edi, 40h ; '@'
0x140004490  mov     ecx, esi
0x140004492  lea     rax, [rbx+8]
0x140004496  mov     edx, edi
0x140004498  xor     ebp, ebp
0x14000449a  test    rcx, rcx
0x14000449d  jz      short loc_1400044BE
0x14000449f  movzx   r9d, word ptr [r8]; unsigned __int16 *
0x1400044a3  test    r9w, r9w
0x1400044a7  jz      short loc_1400044BE
0x1400044a9  mov     [rax], r9w
0x1400044ad  add     r8, 2
0x1400044b1  add     rax, 2
0x1400044b5  dec     rcx
0x1400044b8  sub     rdx, 1
0x1400044bc  jnz     short loc_14000449A
0x1400044be  test    rdx, rdx
0x1400044c1  lea     rcx, [rax-2]
0x1400044c5  lea     r13, aSucceededHr; "SUCCEEDED (hr)"
0x1400044cc  cmovnz  rcx, rax
0x1400044d0  lea     r12, aCntserviceCnts; "CNTService::CNTService"
0x1400044d7  lea     r15, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x1400044de  mov     [rcx], bp
0x1400044e1  jnz     short loc_140004555
0x1400044e3  mov     r8, r12; unsigned __int16 *
0x1400044e6  mov     [rsp+78h+var_58], r13; unsigned __int16 *
0x1400044eb  mov     edx, 2Ch ; ','; unsigned int
0x1400044f0  mov     rcx, r15; unsigned __int16 *
0x1400044f3  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400044f8  call    cs:__imp_IsDebuggerPresent
0x1400044fe  test    eax, eax
0x140004500  lea     rax, aAssert; "ASSERT"
0x140004507  jz      short loc_140004533
0x140004509  mov     r9d, 2Ch ; ','
0x14000450f  mov     [rsp+78h+var_48], r13
0x140004514  mov     [rsp+78h+var_50], rax
0x140004519  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140004520  mov     r8, r15
0x140004523  mov     [rsp+78h+var_58], r12
0x140004528  lea     ecx, [r9-2Ah]; unsigned __int8
0x14000452c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140004531  jmp     short loc_140004555
0x140004533  mov     [rsp+78h+var_50], r13
0x140004538  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000453f  mov     r9, r12
0x140004542  mov     [rsp+78h+var_58], rax
0x140004547  mov     r8d, 2Ch ; ','
0x14000454d  mov     rdx, r15
0x140004550  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140004555  mov     rcx, rsi
0x140004558  lea     rdx, aWindowsMultipo; "@:Windows MultiPoint Server Self-Healin"...
0x14000455f  lea     rax, [rbx+88h]
0x140004566  test    rcx, rcx
0x140004569  jz      short loc_14000458A
0x14000456b  movzx   r8d, word ptr [rdx]
0x14000456f  test    r8w, r8w
0x140004573  jz      short loc_14000458A
0x140004575  mov     [rax], r8w
0x140004579  add     rdx, 2
0x14000457d  add     rax, 2
0x140004581  dec     rcx
0x140004584  sub     rdi, 1
0x140004588  jnz     short loc_140004566
0x14000458a  test    rdi, rdi
0x14000458d  lea     rcx, [rax-2]
0x140004591  cmovnz  rcx, rax
0x140004595  mov     [rcx], bp
0x140004598  jnz     short loc_140004607
0x14000459a  mov     edi, 30h ; '0'
0x14000459f  mov     [rsp+78h+var_58], r13; unsigned __int16 *
0x1400045a4  mov     edx, edi; unsigned int
0x1400045a6  mov     r8, r12; unsigned __int16 *
0x1400045a9  mov     rcx, r15; unsigned __int16 *
0x1400045ac  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400045b1  call    cs:__imp_IsDebuggerPresent
0x1400045b7  test    eax, eax
0x1400045b9  lea     rax, aAssert; "ASSERT"
0x1400045c0  jz      short loc_1400045E8
0x1400045c2  mov     [rsp+78h+var_48], r13
0x1400045c7  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400045ce  mov     [rsp+78h+var_50], rax
0x1400045d3  lea     ecx, [rdi-2Eh]; unsigned __int8
0x1400045d6  mov     r9d, edi
0x1400045d9  mov     [rsp+78h+var_58], r12
0x1400045de  mov     r8, r15
0x1400045e1  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400045e6  jmp     short loc_140004607
0x1400045e8  mov     [rsp+78h+var_50], r13
0x1400045ed  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400045f4  mov     r9, r12
0x1400045f7  mov     [rsp+78h+var_58], rax
0x1400045fc  mov     r8d, edi
0x1400045ff  mov     rdx, r15
0x140004602  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140004607  lea     rcx, aProvidesSelfHe; "@:Provides self-healing for Windows Mul"...
0x14000460e  mov     edx, 100h
0x140004613  lea     rax, [rbx+108h]
0x14000461a  test    rsi, rsi
0x14000461d  jz      short loc_14000463E
0x14000461f  movzx   r8d, word ptr [rcx]
0x140004623  test    r8w, r8w
0x140004627  jz      short loc_14000463E
0x140004629  mov     [rax], r8w
0x14000462d  add     rcx, 2
0x140004631  add     rax, 2
0x140004635  dec     rsi
0x140004638  sub     rdx, 1
0x14000463c  jnz     short loc_14000461A
0x14000463e  test    rdx, rdx
0x140004641  lea     rcx, [rax-2]
0x140004645  cmovnz  rcx, rax
0x140004649  mov     [rcx], bp
0x14000464c  jnz     short loc_1400046BB
0x14000464e  mov     edi, 34h ; '4'
0x140004653  mov     [rsp+78h+var_58], r13; unsigned __int16 *
0x140004658  mov     edx, edi; unsigned int
0x14000465a  mov     r8, r12; unsigned __int16 *
0x14000465d  mov     rcx, r15; unsigned __int16 *
0x140004660  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140004665  call    cs:__imp_IsDebuggerPresent
0x14000466b  test    eax, eax
0x14000466d  lea     rax, aAssert; "ASSERT"
0x140004674  jz      short loc_14000469C
0x140004676  mov     [rsp+78h+var_48], r13
0x14000467b  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140004682  mov     [rsp+78h+var_50], rax
0x140004687  lea     ecx, [rdi-32h]; unsigned __int8
0x14000468a  mov     r9d, edi
0x14000468d  mov     [rsp+78h+var_58], r12
0x140004692  mov     r8, r15
0x140004695  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000469a  jmp     short loc_1400046BB
0x14000469c  mov     [rsp+78h+var_50], r13
0x1400046a1  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400046a8  mov     r9, r12
0x1400046ab  mov     [rsp+78h+var_58], rax
0x1400046b0  mov     r8d, edi
0x1400046b3  mov     rdx, r15
0x1400046b6  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400046bb  mov     dword ptr [rbx+310h], 10h
0x1400046c5  mov     rax, rbx
0x1400046c8  mov     dword ptr [rbx+314h], 1
0x1400046d2  mov     qword ptr [rbx+318h], 2E5h
0x1400046dd  mov     [rbx+320h], rbp
0x1400046e4  mov     [rbx+328h], ebp
0x1400046ea  movups  xmm0, xmmword ptr [rbx+310h]
0x1400046f1  mov     [rbx+308h], rbp
0x1400046f8  movups  xmm1, xmmword ptr [rbx+31Ch]
0x1400046ff  mov     qword ptr [rbx+348h], 0FFFFFFFFFFFFFFFFh
0x14000470a  movups  xmmword ptr [rbx+32Ch], xmm0
0x140004711  movups  xmmword ptr [rbx+338h], xmm1
0x140004718  add     rsp, 40h
0x14000471c  pop     r15
0x14000471e  pop     r13
0x140004720  pop     r12
0x140004722  pop     rdi
0x140004723  pop     rsi
0x140004724  pop     rbp
0x140004725  pop     rbx
0x140004726  retn
```
