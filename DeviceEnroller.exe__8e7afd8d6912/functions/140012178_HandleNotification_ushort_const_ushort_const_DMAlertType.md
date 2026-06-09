# HandleNotification(ushort const *,ushort const *,DMAlertType)

- ea: `0x140012178`
- end: `0x1400123eb`
- name: `?HandleNotification@@YAJPEBG0W4DMAlertType@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x140012178`
- `0x14002f150`
- `0x140031bc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001230a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001231c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140012362`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001230a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001231c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140012362`
- `dmEnrollEngine!GetEnrollmentType` at `0x140012293`
- `dmEnrollEngine!GetEnrollmentType` at `0x140012293`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1400122ae`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1400122ae`
- `omadmapi!__imp_OmaDmInitiateSessionFullSync` at `0x14001239c`
- `omadmapi!__imp_OmaDmInitiateSessionFullSync` at `0x14001239c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400123b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400123b9`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x14001222a`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x14001222a`
- `RPCRT4!UuidFromStringW` at `0x140012256`
- `RPCRT4!UuidFromStringW` at `0x140012267`
- `RPCRT4!UuidFromStringW` at `0x140012256`
- `RPCRT4!UuidFromStringW` at `0x140012267`

## string_xrefs

- `0x140012244`: `com.microsoft:mdm.oseditionupgrade`
- `0x140012211`: `com.microsoft:mdm.osmode`

## pseudocode

```c
__int64 __fastcall HandleNotification(unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  int SwV; // ebx
  __int64 v7; // rdx
  const unsigned __int16 *v8; // r14
  const wchar_t *v9; // r12
  const wchar_t *v10; // r13
  const unsigned __int16 *v11; // rcx
  const unsigned __int16 *v12; // r8
  int v14; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  UUID v17; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v19; // [rsp+68h] [rbp-98h]
  const wchar_t *v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+80h] [rbp-80h]
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[528]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v16 = 63;
  Uuid = 0;
  hMem = 0;
  memset_0(v23, 0, 0x208u);
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      SwV = -2147418113;
      v7 = 1248;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
        (const char *)(unsigned int)SwV,
        v14);
      return (unsigned int)SwV;
    }
    v8 = L"Win10 S Mode alert to server after user logs on";
    v9 = L"com.microsoft:mdm.osmode";
    v10 = L" ";
  }
  else
  {
    SwV = DMCSP_DevDetail_GetSwV(260, v23);
    if ( SwV < 0 )
    {
      v7 = 1233;
      goto LABEL_4;
    }
    v8 = L"OS Edition Upgrade alert to server after user logs on";
    v9 = L"com.microsoft:mdm.oseditionupgrade";
    v10 = (const wchar_t *)v23;
  }
  if ( UuidFromStringW(a1, &Uuid) )
  {
    SwV = UuidFromStringW(a1, &Uuid) | 0x80010000;
    v7 = 1250;
    goto LABEL_4;
  }
  v17 = Uuid;
  SwV = GetEnrollmentType(&v17, &v16);
  if ( SwV < 0 )
  {
    v7 = 1251;
    goto LABEL_4;
  }
  SwV = DmGetActiveUserSid((unsigned __int16 **)&hMem);
  if ( (int)(SwV + 0x80000000) >= 0 && SwV != -2147024769 )
  {
    v7 = 1254;
    goto LABEL_4;
  }
  *(_QWORD *)&v17.Data1 = &hMem;
  v17.Data4[0] = 1;
  if ( !hMem || (unsigned int)_o__wcsicmp(a2, L"S-1-1-0") && (unsigned int)_o__wcsicmp(a2, hMem) )
  {
    SwV = ScheduleUserLogonTask((__int64)a1, a2, (const unsigned __int16 *)a3);
  }
  else
  {
    memset_0(v18, 0, 0x40u);
    v18[0] = 64;
    v18[1] = 1226;
    v19 = v9;
    v20 = v10;
    v21 = 1;
    if ( (unsigned int)_o__wcsicmp(a2, L"S-1-1-0") )
      v11 = a2;
    else
      v11 = 0;
    SwV = OmaDmInitiateSessionFullSync(v11, a1, 1, 2, v18, 1, 0, 26);
    if ( SwV >= 0 )
      DeleteTask(v8, a2, v12);
  }
  LocalFree(hMem);
  return (unsigned int)SwV;
}

```

## disassembly

```asm
0x140012178  mov     [rsp-8+arg_18], rbx
0x14001217d  push    rbp
0x14001217e  push    rsi
0x14001217f  push    rdi
0x140012180  push    r12
0x140012182  push    r13
0x140012184  push    r14
0x140012186  push    r15
0x140012188  lea     rbp, [rsp-1D0h]
0x140012190  sub     rsp, 2D0h
0x140012197  mov     rax, cs:__security_cookie
0x14001219e  xor     rax, rsp
0x1400121a1  mov     [rbp+200h+var_40], rax
0x1400121a8  mov     r15d, r8d
0x1400121ab  mov     rdi, rdx
0x1400121ae  mov     rsi, rcx
0x1400121b1  mov     [rsp+300h+var_2B8], 3Fh ; '?'
0x1400121b9  xorps   xmm0, xmm0
0x1400121bc  movups  xmmword ptr [rbp+200h+Uuid.Data1], xmm0
0x1400121c0  mov     [rsp+300h+hMem], 0
0x1400121c9  xor     edx, edx; Val
0x1400121cb  mov     r8d, 208h; Size
0x1400121d1  lea     rcx, [rbp+200h+var_250]; void *
0x1400121d5  call    memset_0
0x1400121da  test    r15d, r15d
0x1400121dd  jz      short loc_140012221
0x1400121df  cmp     r15d, 1
0x1400121e3  jz      short loc_14001220A
0x1400121e5  mov     ebx, 8000FFFFh
0x1400121ea  mov     edx, 4E0h; void *
0x1400121ef  mov     rcx, [rbp+208h]; this
0x1400121f6  mov     r9d, ebx; char *
0x1400121f9  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012205  jmp     loc_1400123BF
0x14001220a  lea     r14, aWin10SModeAler; "Win10 S Mode alert to server after user"...
0x140012211  lea     r12, aComMicrosoftMd_0; "com.microsoft:mdm.osmode"
0x140012218  lea     r13, asc_140062344; " "
0x14001221f  jmp     short loc_14001224F
0x140012221  lea     rdx, [rbp+200h+var_250]
0x140012225  mov     ecx, 104h
0x14001222a  call    cs:__imp_DMCSP_DevDetail_GetSwV
0x140012230  mov     ebx, eax
0x140012232  test    eax, eax
0x140012234  jns     short loc_14001223D
0x140012236  mov     edx, 4D1h
0x14001223b  jmp     short loc_1400121EF
0x14001223d  lea     r14, aOsEditionUpgra_0; "OS Edition Upgrade alert to server afte"...
0x140012244  lea     r12, aComMicrosoftMd_4; "com.microsoft:mdm.oseditionupgrade"
0x14001224b  lea     r13, [rbp+200h+var_250]
0x14001224f  lea     rdx, [rbp+200h+Uuid]; Uuid
0x140012253  mov     rcx, rsi; StringUuid
0x140012256  call    cs:__imp_UuidFromStringW
0x14001225c  test    eax, eax
0x14001225e  jz      short loc_14001227F
0x140012260  lea     rdx, [rbp+200h+Uuid]; Uuid
0x140012264  mov     rcx, rsi; StringUuid
0x140012267  call    cs:__imp_UuidFromStringW
0x14001226d  mov     ebx, eax
0x14001226f  or      ebx, 80010000h
0x140012275  mov     edx, 4E2h
0x14001227a  jmp     loc_1400121EF
0x14001227f  movaps  xmm0, xmmword ptr [rbp+200h+Uuid.Data1]
0x140012283  movdqa  [rsp+300h+var_2B0], xmm0
0x140012289  lea     rdx, [rsp+300h+var_2B8]
0x14001228e  lea     rcx, [rsp+300h+var_2B0]
0x140012293  call    cs:__imp_GetEnrollmentType
0x140012299  mov     ebx, eax
0x14001229b  test    eax, eax
0x14001229d  jns     short loc_1400122A9
0x14001229f  mov     edx, 4E3h
0x1400122a4  jmp     loc_1400121EF
0x1400122a9  lea     rcx, [rsp+300h+hMem]
0x1400122ae  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1400122b4  mov     ebx, eax
0x1400122b6  mov     eax, 80000000h
0x1400122bb  lea     ecx, [rbx+rax]
0x1400122be  test    eax, ecx
0x1400122c0  jnz     short loc_1400122D4
0x1400122c2  cmp     ebx, 8007007Fh
0x1400122c8  jz      short loc_1400122D4
0x1400122ca  mov     edx, 4E6h
0x1400122cf  jmp     loc_1400121EF
0x1400122d4  lea     rax, [rsp+300h+hMem]
0x1400122d9  mov     qword ptr [rsp+300h+var_2B0], rax
0x1400122de  mov     byte ptr [rsp+300h+var_2B0+8], 1
0x1400122e3  cmp     [rsp+300h+hMem], 0
0x1400122e9  jnz     short loc_140012300
0x1400122eb  mov     r8d, r15d
0x1400122ee  mov     rdx, rdi
0x1400122f1  mov     rcx, rsi
0x1400122f4  call    ?ScheduleUserLogonTask@@YAJPEBG0W4DMAlertType@@@Z; ScheduleUserLogonTask(ushort const *,ushort const *,DMAlertType)
0x1400122f9  mov     ebx, eax
0x1400122fb  jmp     loc_1400123B4
0x140012300  lea     rdx, aS110; "S-1-1-0"
0x140012307  mov     rcx, rdi
0x14001230a  call    cs:__imp__o__wcsicmp
0x140012310  test    eax, eax
0x140012312  jz      short loc_140012326
0x140012314  mov     rdx, [rsp+300h+hMem]
0x140012319  mov     rcx, rdi
0x14001231c  call    cs:__imp__o__wcsicmp
0x140012322  test    eax, eax
0x140012324  jnz     short loc_1400122EB
0x140012326  mov     ebx, 40h ; '@'
0x14001232b  mov     r8d, ebx; Size
0x14001232e  xor     edx, edx; Val
0x140012330  lea     rcx, [rsp+300h+var_2A0]; void *
0x140012335  call    memset_0
0x14001233a  mov     [rsp+300h+var_2A0], ebx
0x14001233e  mov     [rsp+300h+var_29C], 4CAh
0x140012346  mov     [rsp+300h+var_298], r12
0x14001234b  mov     [rsp+300h+var_288], r13
0x140012350  mov     ebx, 1
0x140012355  mov     [rbp+200h+var_280], ebx
0x140012358  lea     rdx, aS110; "S-1-1-0"
0x14001235f  mov     rcx, rdi
0x140012362  call    cs:__imp__o__wcsicmp
0x140012368  mov     [rsp+300h+var_2C8], 1Ah
0x140012370  lea     r9d, [rbx+1]
0x140012374  mov     r8d, ebx
0x140012377  mov     rdx, rsi
0x14001237a  mov     [rsp+300h+var_2D0], 0
0x140012383  mov     [rsp+300h+var_2D8], ebx
0x140012387  test    eax, eax
0x140012389  lea     rax, [rsp+300h+var_2A0]
0x14001238e  mov     [rsp+300h+var_2E0], rax
0x140012393  jnz     short loc_140012399
0x140012395  xor     ecx, ecx
0x140012397  jmp     short loc_14001239C
0x140012399  mov     rcx, rdi
0x14001239c  call    cs:__imp_OmaDmInitiateSessionFullSync
0x1400123a2  mov     ebx, eax
0x1400123a4  test    eax, eax
0x1400123a6  js      short loc_1400123B4
0x1400123a8  mov     rdx, rdi; unsigned __int16 *
0x1400123ab  mov     rcx, r14; unsigned __int16 *
0x1400123ae  call    ?DeleteTask@@YAJPEBG00@Z; DeleteTask(ushort const *,ushort const *,ushort const *)
0x1400123b3  nop
0x1400123b4  mov     rcx, [rsp+300h+hMem]; hMem
0x1400123b9  call    cs:__imp_LocalFree
0x1400123bf  mov     eax, ebx
0x1400123c1  mov     rcx, [rbp+200h+var_40]
0x1400123c8  xor     rcx, rsp; StackCookie
0x1400123cb  call    __security_check_cookie
0x1400123d0  mov     rbx, [rsp+300h+arg_18]
0x1400123d8  add     rsp, 2D0h
0x1400123df  pop     r15
0x1400123e1  pop     r14
0x1400123e3  pop     r13
0x1400123e5  pop     r12
0x1400123e7  pop     rdi
0x1400123e8  pop     rsi
0x1400123e9  pop     rbp
0x1400123ea  retn
```
