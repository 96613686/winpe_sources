# IP_SECURITY_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x1800200e0`
- end: `0x180020436`
- name: `?SetAboProperties@IP_SECURITY_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `854`
- prototype: `int(IP_SECURITY_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002990`
- `0x180003460`
- `0x18000a838`
- `0x18001bd20`
- `0x1800200e0`
- `0x180026f60`
- `0x18002a330`
- `0x18002a5d4`
- `0x18002a8cc`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180020313`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180020313`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x18002021d`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x18002021d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002013c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002013c`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800202ff`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800202ff`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180020365`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180020365`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180020406`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180020406`

## pseudocode

```c
__int64 __fastcall IP_SECURITY_CUSTOM_MAPPER::SetAboProperties(
        IP_SECURITY_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  char *v7; // rax
  DWORD *v8; // rbx
  unsigned int v9; // edx
  int v10; // edi
  unsigned int v11; // esi
  unsigned int v12; // r8d
  int v13; // eax
  char *Str; // rax
  unsigned int v15; // r9d
  __int64 v17; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-61h] BYREF
  int v19; // [rsp+3Ch] [rbp-5Dh] BYREF
  unsigned int v20; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-55h] BYREF
  __int64 v22; // [rsp+48h] [rbp-51h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-39h] BYREF
  struct _METADATA_RECORD v26; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v27[56]; // [rsp+90h] [rbp-9h] BYREF

  v22 = 0;
  v17 = 0;
  v20 = 0;
  v19 = 0;
  v24 = 0;
  v25 = 0;
  v23 = 0;
  v18 = 0;
  STRA::STRA((STRA *)v27);
  if ( a2 && a3 && a4 )
  {
    v26.dwMDIdentifier = *((_DWORD *)a2 + 36);
    v26.dwMDUserType = *((_DWORD *)a2 + 37);
    v26.dwMDDataType = *((_DWORD *)a2 + 38);
    v26.dwMDAttributes = *((_DWORD *)a2 + 39);
    memset(&v26.dwMDDataLen, 0, 24);
    v7 = (char *)operator new(0x28u);
    v8 = (DWORD *)v7;
    if ( v7 )
    {
      *(_QWORD *)(v7 + 12) = 0;
      *(_QWORD *)v7 = 0;
      *((_DWORD *)v7 + 2) = 0;
      if ( (unsigned int)ADDRESS_CHECK::BindCheckList((ADDRESS_CHECK *)v7) )
      {
        v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 40LL))(
                a3,
                &v22);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 24LL))(v22, &v20);
          if ( v10 >= 0 )
          {
            if ( v20 )
            {
              v11 = 0;
              while ( 1 )
              {
                v21 = 0;
                v18 = 0;
                STRA::Reset((STRA *)v27);
                v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, v11, &v17);
                if ( v10 < 0 )
                  break;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
                        v17,
                        L"allowed",
                        &v19,
                        0,
                        0);
                if ( v10 < 0 )
                  break;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                        v17,
                        L"ipAddress",
                        &v24,
                        0,
                        0);
                if ( v10 < 0 )
                  break;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                        v17,
                        L"subnetMask",
                        &v25,
                        0,
                        0);
                if ( v10 < 0 )
                  break;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                        v17,
                        L"domainName",
                        &v23,
                        0,
                        0);
                if ( v10 < 0 )
                  break;
                v10 = STRA::CopyW((STRA *)v27, v23);
                if ( v10 < 0 )
                  break;
                if ( STRA::QueryCCH((STRA *)v27) )
                {
                  Str = STRA::QueryStr((STRA *)v27);
                  v13 = ADDRESS_CHECK::AddName((ADDRESS_CHECK *)v8, v19, Str, v15);
                }
                else
                {
                  v10 = IPStrToDWord(v24, &v21);
                  if ( v10 < 0 )
                    break;
                  v10 = IPStrToDWord(v25, &v18);
                  if ( v10 < 0 )
                    break;
                  v13 = ADDRESS_CHECK::AddAddr(
                          (ADDRESS_CHECK *)v8,
                          v19,
                          v12,
                          (unsigned __int8 *)&v18,
                          (unsigned __int8 *)&v21);
                }
                if ( !v13 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                  v17 = 0;
                }
                if ( ++v11 >= v20 )
                {
                  v26.pbMDData = *(unsigned __int8 **)v8;
                  v26.dwMDDataLen = v8[3];
                  v10 = ABO_NODE::SetDataByMapping(a4, &v26, a2);
                  break;
                }
              }
            }
          }
        }
      }
      else
      {
        v10 = -2147024888;
      }
      ADDRESS_CHECK::`scalar deleting destructor'((ADDRESS_CHECK *)v8, v9);
    }
    else
    {
      v10 = -2147024888;
    }
  }
  else
  {
    v10 = -2147024809;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  STRA::~STRA((STRA *)v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800200e0  mov     [rsp-8+arg_0], rbx
0x1800200e5  mov     [rsp-8+arg_8], rsi
0x1800200ea  push    rbp
0x1800200eb  push    rdi
0x1800200ec  push    r12
0x1800200ee  push    r14
0x1800200f0  push    r15
0x1800200f2  lea     rbp, [rsp-37h]
0x1800200f7  sub     rsp, 0D0h
0x1800200fe  mov     rax, cs:__security_cookie
0x180020105  xor     rax, rsp
0x180020108  mov     [rbp+57h+var_28], rax
0x18002010c  xor     r12d, r12d
0x18002010f  lea     rcx, [rbp+57h+var_60]
0x180020113  mov     [rbp+57h+var_A8], r12
0x180020117  mov     r15, r9
0x18002011a  mov     [rbp+57h+var_C0], r12
0x18002011e  mov     rdi, r8
0x180020121  mov     [rbp+57h+var_B0], r12d
0x180020125  mov     r14, rdx
0x180020128  mov     [rbp+57h+var_B4], r12d
0x18002012c  mov     [rbp+57h+var_98], r12
0x180020130  mov     [rbp+57h+var_90], r12
0x180020134  mov     [rbp+57h+var_A0], r12
0x180020138  mov     [rbp+57h+var_B8], r12d
0x18002013c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180020142  test    r14, r14
0x180020145  jz      loc_1800203CB
0x18002014b  test    rdi, rdi
0x18002014e  jz      loc_1800203CB
0x180020154  test    r15, r15
0x180020157  jz      loc_1800203CB
0x18002015d  mov     eax, [r14+90h]
0x180020164  lea     ecx, [r12+28h]; Size
0x180020169  mov     [rbp+57h+var_88.dwMDIdentifier], eax
0x18002016c  xorps   xmm0, xmm0
0x18002016f  mov     eax, [r14+94h]
0x180020176  mov     [rbp+57h+var_88.dwMDUserType], eax
0x180020179  mov     eax, [r14+98h]
0x180020180  mov     [rbp+57h+var_88.dwMDDataType], eax
0x180020183  mov     eax, [r14+9Ch]
0x18002018a  mov     [rbp+57h+var_88.dwMDAttributes], eax
0x18002018d  movdqu  xmmword ptr [rbp+57h+var_88.dwMDDataLen], xmm0
0x180020192  mov     qword ptr [rbp+57h+var_88.dwMDDataTag], r12
0x180020196  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002019b  mov     rbx, rax
0x18002019e  test    rax, rax
0x1800201a1  jz      loc_1800203C4
0x1800201a7  mov     rcx, rax; this
0x1800201aa  mov     [rax+0Ch], r12
0x1800201ae  mov     [rax], r12
0x1800201b1  mov     [rax+8], r12d
0x1800201b5  call    ?BindCheckList@ADDRESS_CHECK@@QEAAHXZ; ADDRESS_CHECK::BindCheckList(void)
0x1800201ba  test    eax, eax
0x1800201bc  jnz     short loc_1800201C8
0x1800201be  mov     edi, 80070008h
0x1800201c3  jmp     loc_1800203BA
0x1800201c8  mov     rax, [rdi]
0x1800201cb  lea     rdx, [rbp+57h+var_A8]
0x1800201cf  mov     rcx, rdi
0x1800201d2  mov     rax, [rax+28h]
0x1800201d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201db  mov     edi, eax
0x1800201dd  test    eax, eax
0x1800201df  js      loc_1800203BA
0x1800201e5  mov     rcx, [rbp+57h+var_A8]
0x1800201e9  lea     rdx, [rbp+57h+var_B0]
0x1800201ed  mov     rax, [rcx]
0x1800201f0  mov     rax, [rax+18h]
0x1800201f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201f9  mov     edi, eax
0x1800201fb  test    eax, eax
0x1800201fd  js      loc_1800203BA
0x180020203  mov     eax, [rbp+57h+var_B0]
0x180020206  test    eax, eax
0x180020208  jz      loc_1800203BA
0x18002020e  mov     esi, r12d
0x180020211  lea     rcx, [rbp+57h+var_60]
0x180020215  mov     [rbp+57h+var_AC], r12d
0x180020219  mov     [rbp+57h+var_B8], r12d
0x18002021d  call    cs:__imp_?Reset@STRA@@QEAAXXZ; STRA::Reset(void)
0x180020223  mov     rcx, [rbp+57h+var_A8]
0x180020227  lea     r8, [rbp+57h+var_C0]
0x18002022b  mov     edx, esi
0x18002022d  mov     rax, [rcx]
0x180020230  mov     rax, [rax+20h]
0x180020234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020239  mov     edi, eax
0x18002023b  test    eax, eax
0x18002023d  js      loc_1800203BA
0x180020243  mov     rcx, [rbp+57h+var_C0]
0x180020247  lea     r8, [rbp+57h+var_B4]
0x18002024b  xor     r9d, r9d
0x18002024e  mov     [rsp+0F0h+var_D0], r12
0x180020253  lea     rdx, aAllowed; "allowed"
0x18002025a  mov     rax, [rcx]
0x18002025d  mov     rax, [rax+48h]
0x180020261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020266  mov     edi, eax
0x180020268  test    eax, eax
0x18002026a  js      loc_1800203BA
0x180020270  mov     rcx, [rbp+57h+var_C0]
0x180020274  lea     r8, [rbp+57h+var_98]
0x180020278  xor     r9d, r9d
0x18002027b  mov     [rsp+0F0h+var_D0], r12
0x180020280  lea     rdx, aIpaddress; "ipAddress"
0x180020287  mov     rax, [rcx]
0x18002028a  mov     rax, [rax+40h]
0x18002028e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020293  mov     edi, eax
0x180020295  test    eax, eax
0x180020297  js      loc_1800203BA
0x18002029d  mov     rcx, [rbp+57h+var_C0]
0x1800202a1  lea     r8, [rbp+57h+var_90]
0x1800202a5  xor     r9d, r9d
0x1800202a8  mov     [rsp+0F0h+var_D0], r12
0x1800202ad  lea     rdx, aSubnetmask; "subnetMask"
0x1800202b4  mov     rax, [rcx]
0x1800202b7  mov     rax, [rax+40h]
0x1800202bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202c0  mov     edi, eax
0x1800202c2  test    eax, eax
0x1800202c4  js      loc_1800203BA
0x1800202ca  mov     rcx, [rbp+57h+var_C0]
0x1800202ce  lea     r8, [rbp+57h+var_A0]
0x1800202d2  xor     r9d, r9d
0x1800202d5  mov     [rsp+0F0h+var_D0], r12
0x1800202da  lea     rdx, aDomainname; "domainName"
0x1800202e1  mov     rax, [rcx]
0x1800202e4  mov     rax, [rax+40h]
0x1800202e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202ed  mov     edi, eax
0x1800202ef  test    eax, eax
0x1800202f1  js      loc_1800203BA
0x1800202f7  mov     rdx, [rbp+57h+var_A0]
0x1800202fb  lea     rcx, [rbp+57h+var_60]
0x1800202ff  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180020305  mov     edi, eax
0x180020307  test    eax, eax
0x180020309  js      loc_1800203BA
0x18002030f  lea     rcx, [rbp+57h+var_60]
0x180020313  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180020319  test    eax, eax
0x18002031b  jnz     short loc_180020361
0x18002031d  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180020321  lea     rdx, [rbp+57h+var_AC]; unsigned int *
0x180020325  call    ?IPStrToDWord@@YAJPEBGPEAK@Z; IPStrToDWord(ushort const *,ulong *)
0x18002032a  mov     edi, eax
0x18002032c  test    eax, eax
0x18002032e  js      loc_1800203BA
0x180020334  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180020338  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x18002033c  call    ?IPStrToDWord@@YAJPEBGPEAK@Z; IPStrToDWord(ushort const *,ulong *)
0x180020341  mov     edi, eax
0x180020343  test    eax, eax
0x180020345  js      short loc_1800203BA
0x180020347  mov     edx, [rbp+57h+var_B4]; int
0x18002034a  lea     rax, [rbp+57h+var_AC]
0x18002034e  lea     r9, [rbp+57h+var_B8]; unsigned __int8 *
0x180020352  mov     [rsp+0F0h+var_D0], rax; unsigned __int8 *
0x180020357  mov     rcx, rbx; this
0x18002035a  call    ?AddAddr@ADDRESS_CHECK@@QEAAHHKPEAE0@Z; ADDRESS_CHECK::AddAddr(int,ulong,uchar *,uchar *)
0x18002035f  jmp     short loc_180020379
0x180020361  lea     rcx, [rbp+57h+var_60]
0x180020365  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002036b  mov     edx, [rbp+57h+var_B4]; int
0x18002036e  mov     rcx, rbx; this
0x180020371  mov     r8, rax; char *
0x180020374  call    ?AddName@ADDRESS_CHECK@@QEAAHHPEADK@Z; ADDRESS_CHECK::AddName(int,char *,ulong)
0x180020379  test    eax, eax
0x18002037b  jnz     short loc_180020391
0x18002037d  mov     rcx, [rbp+57h+var_C0]
0x180020381  mov     rax, [rcx]
0x180020384  mov     rax, [rax+10h]
0x180020388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002038d  mov     [rbp+57h+var_C0], r12
0x180020391  inc     esi
0x180020393  cmp     esi, [rbp+57h+var_B0]
0x180020396  jb      loc_180020211
0x18002039c  mov     rax, [rbx]
0x18002039f  lea     rdx, [rbp+57h+var_88]; struct _METADATA_RECORD *
0x1800203a3  mov     [rbp+57h+var_88.pbMDData], rax
0x1800203a7  mov     r8, r14; struct PROPERTY_MAPPING *
0x1800203aa  mov     eax, [rbx+0Ch]
0x1800203ad  mov     rcx, r15; this
0x1800203b0  mov     [rbp+57h+var_88.dwMDDataLen], eax
0x1800203b3  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x1800203b8  mov     edi, eax
0x1800203ba  mov     rcx, rbx; this
0x1800203bd  call    ??_GADDRESS_CHECK@@QEAAPEAXI@Z; ADDRESS_CHECK::`scalar deleting destructor'(uint)
0x1800203c2  jmp     short loc_1800203D0
0x1800203c4  mov     edi, 80070008h
0x1800203c9  jmp     short loc_1800203D0
0x1800203cb  mov     edi, 80070057h
0x1800203d0  mov     rcx, [rbp+57h+var_C0]
0x1800203d4  test    rcx, rcx
0x1800203d7  jz      short loc_1800203E9
0x1800203d9  mov     rax, [rcx]
0x1800203dc  mov     rax, [rax+10h]
0x1800203e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203e5  mov     [rbp+57h+var_C0], r12
0x1800203e9  mov     rcx, [rbp+57h+var_A8]
0x1800203ed  test    rcx, rcx
0x1800203f0  jz      short loc_180020402
0x1800203f2  mov     rax, [rcx]
0x1800203f5  mov     rax, [rax+10h]
0x1800203f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203fe  mov     [rbp+57h+var_A8], r12
0x180020402  lea     rcx, [rbp+57h+var_60]
0x180020406  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002040c  mov     eax, edi
0x18002040e  mov     rcx, [rbp+57h+var_28]
0x180020412  xor     rcx, rsp; StackCookie
0x180020415  call    __security_check_cookie
0x18002041a  lea     r11, [rsp+0F0h+var_20]
0x180020422  mov     rbx, [r11+30h]
0x180020426  mov     rsi, [r11+38h]
0x18002042a  mov     rsp, r11
0x18002042d  pop     r15
0x18002042f  pop     r14
0x180020431  pop     r12
0x180020433  pop     rdi
0x180020434  pop     rbp
0x180020435  retn
```
