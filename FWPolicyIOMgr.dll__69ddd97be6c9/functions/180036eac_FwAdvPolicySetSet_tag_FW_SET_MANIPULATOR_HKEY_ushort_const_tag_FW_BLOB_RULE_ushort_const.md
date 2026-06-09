# FwAdvPolicySetSet(_tag_FW_SET_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE *,ushort const *)

- ea: `0x180036eac`
- end: `0x1800371b4`
- name: `?FwAdvPolicySetSet@@YAJPEAU_tag_FW_SET_MANIPULATOR@@PEAUHKEY__@@PEBGPEAU_tag_FW_BLOB_RULE@@2@Z`
- size: `776`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *), HKEY, const unsigned __int16 *, struct _tag_FW_BLOB_RULE *, LPCWSTR lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030ac0`

## callees

- `0x1800042c4`
- `0x18001e9ac`
- `0x18001ec98`
- `0x18001f650`
- `0x180036d3c`
- `0x180036eac`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180036ffd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180036ffd`
- `fwbase!FwFree` at `0x18003717f`
- `fwbase!FwFree` at `0x18003717f`
- `fwbase!FwRegOpenKey` at `0x180036f23`
- `fwbase!FwRegOpenKey` at `0x180036f23`
- `fwbase!FwRegCloseKey` at `0x180037189`
- `fwbase!FwRegCloseKey` at `0x180037193`
- `fwbase!FwRegCloseKey` at `0x180037189`
- `fwbase!FwRegCloseKey` at `0x180037193`
- `fwbase!FwRegCreateKey` at `0x180037108`
- `fwbase!FwRegCreateKey` at `0x180037108`
- `fwbase!FwRegDeleteKey` at `0x1800370c3`
- `fwbase!FwRegDeleteKey` at `0x1800370c3`

## pseudocode

```c
__int64 __fastcall FwAdvPolicySetSet(
        __int64 (__fastcall **a1)(struct _tag_FW_BLOB_RULE *),
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_FW_BLOB_RULE *a4,
        LPCWSTR lpString1)
{
  int MergedGPODefaultID; // eax
  unsigned int v10; // ebx
  LPCOLESTR v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int16 *v14; // rdi
  LPCWSTR *v15; // rax
  unsigned int v17; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-28h] BYREF
  __int64 v20; // [rsp+48h] [rbp-20h] BYREF
  int v21; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v20 = 0;
  v17 = 0;
  v21 = 0;
  v19 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  MergedGPODefaultID = FwRegOpenKey(a2, a3, 15, &hKey, &v21);
  v10 = MergedGPODefaultID;
  if ( MergedGPODefaultID < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 63;
LABEL_42:
      v13 = (unsigned int)MergedGPODefaultID;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  if ( !v21 )
  {
    v13 = 2147942402LL;
    v10 = -2147024894;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_44;
    v12 = 64;
    goto LABEL_43;
  }
  MergedGPODefaultID = FwGetMergedGPODefaultID(hKey, lpString1, &v19);
  v10 = MergedGPODefaultID;
  if ( MergedGPODefaultID >= 0 )
  {
    v14 = *(unsigned __int16 **)a1[6](a4);
    if ( v19 )
    {
      v15 = (LPCWSTR *)a1[6](a4);
      if ( !lstrcmpiW(lpString1, *v15) )
        v14 = v19;
    }
    MergedGPODefaultID = FwAdvPolicyLookForSetID(hKey, v14, &v17);
    v10 = MergedGPODefaultID;
    if ( MergedGPODefaultID < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 66;
        goto LABEL_42;
      }
      goto LABEL_44;
    }
    if ( v17 <= 1 )
    {
      if ( v17 )
      {
        MergedGPODefaultID = FwRegDeleteKey(hKey, v14);
        v10 = MergedGPODefaultID;
        if ( MergedGPODefaultID >= 0 )
        {
          MergedGPODefaultID = FwRegCreateKey(hKey, v14, 15, &v20);
          v10 = MergedGPODefaultID;
          if ( MergedGPODefaultID >= 0 )
          {
            MergedGPODefaultID = ((__int64 (__fastcall *)(struct _tag_FW_BLOB_RULE *, __int64))a1[11])(a4, v20);
            v10 = MergedGPODefaultID;
            if ( MergedGPODefaultID < 0 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v12 = 71;
                goto LABEL_42;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v12 = 70;
              goto LABEL_42;
            }
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v12 = 69;
            goto LABEL_42;
          }
        }
        goto LABEL_44;
      }
      v13 = 2147942402LL;
      v10 = -2147024894;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_44;
      v12 = 68;
    }
    else
    {
      v10 = -2147418113;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_44;
      v12 = 67;
      v13 = 2147549183LL;
    }
LABEL_43:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v13);
    goto LABEL_44;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = 65;
    goto LABEL_42;
  }
LABEL_44:
  FwFree(v19);
  FwRegCloseKey(v20);
  FwRegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x180036eac  push    rbp
0x180036eae  push    rbx
0x180036eaf  push    rsi
0x180036eb0  push    rdi
0x180036eb1  push    r14
0x180036eb3  push    r15
0x180036eb5  mov     rbp, rsp
0x180036eb8  sub     rsp, 68h
0x180036ebc  mov     rax, cs:__security_cookie
0x180036ec3  xor     rax, rsp
0x180036ec6  mov     [rbp+var_10], rax
0x180036eca  mov     r15, [rbp+lpString1]
0x180036ece  mov     r14, r9
0x180036ed1  mov     [rbp+hKey], 0
0x180036ed9  mov     rdi, r8
0x180036edc  mov     [rbp+var_20], 0
0x180036ee4  mov     rbx, rdx
0x180036ee7  mov     [rbp+var_38], 0
0x180036eee  mov     rsi, rcx
0x180036ef1  mov     [rbp+var_18], 0
0x180036ef8  mov     [rbp+var_28], 0
0x180036f00  test    rdx, rdx
0x180036f03  jnz     short loc_180036F0A
0x180036f05  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180036f0a  lea     rax, [rbp+var_18]
0x180036f0e  mov     r8d, 0Fh
0x180036f14  lea     r9, [rbp+hKey]
0x180036f18  mov     [rsp+68h+var_48], rax
0x180036f1d  mov     rdx, rdi
0x180036f20  mov     rcx, rbx
0x180036f23  call    cs:__imp_FwRegOpenKey
0x180036f29  mov     ebx, eax
0x180036f2b  test    eax, eax
0x180036f2d  jns     short loc_180036F5A
0x180036f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f36  lea     rdx, WPP_GLOBAL_Control
0x180036f3d  cmp     rcx, rdx
0x180036f40  jz      loc_18003717B
0x180036f46  test    byte ptr [rcx+1Ch], 1
0x180036f4a  jz      loc_18003717B
0x180036f50  mov     edx, 3Fh ; '?'
0x180036f55  jmp     loc_180037168
0x180036f5a  cmp     [rbp+var_18], 0
0x180036f5e  jnz     short loc_180036F94
0x180036f60  mov     r9d, 80070002h
0x180036f66  mov     ebx, r9d
0x180036f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f70  lea     rdx, WPP_GLOBAL_Control
0x180036f77  cmp     rcx, rdx
0x180036f7a  jz      loc_18003717B
0x180036f80  test    byte ptr [rcx+1Ch], 1
0x180036f84  jz      loc_18003717B
0x180036f8a  mov     edx, 40h ; '@'
0x180036f8f  jmp     loc_18003716B
0x180036f94  mov     rcx, [rbp+hKey]; HKEY
0x180036f98  lea     r8, [rbp+var_28]; unsigned __int16 **
0x180036f9c  mov     rdx, r15; unsigned __int16 *
0x180036f9f  call    ?FwGetMergedGPODefaultID@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; FwGetMergedGPODefaultID(HKEY__ *,ushort const *,ushort * *)
0x180036fa4  mov     ebx, eax
0x180036fa6  test    eax, eax
0x180036fa8  jns     short loc_180036FD5
0x180036faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fb1  lea     rdx, WPP_GLOBAL_Control
0x180036fb8  cmp     rcx, rdx
0x180036fbb  jz      loc_18003717B
0x180036fc1  test    byte ptr [rcx+1Ch], 1
0x180036fc5  jz      loc_18003717B
0x180036fcb  mov     edx, 41h ; 'A'
0x180036fd0  jmp     loc_180037168
0x180036fd5  mov     rax, [rsi+30h]
0x180036fd9  mov     rcx, r14
0x180036fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe1  cmp     [rbp+var_28], 0
0x180036fe6  mov     rdi, [rax]
0x180036fe9  jz      short loc_18003700A
0x180036feb  mov     rax, [rsi+30h]
0x180036fef  mov     rcx, r14
0x180036ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ff7  mov     rcx, r15; lpString1
0x180036ffa  mov     rdx, [rax]; lpString2
0x180036ffd  call    cs:__imp_lstrcmpiW
0x180037003  test    eax, eax
0x180037005  cmovz   rdi, [rbp+var_28]
0x18003700a  mov     rcx, [rbp+hKey]; hKey
0x18003700e  lea     r8, [rbp+var_38]; unsigned int *
0x180037012  mov     rdx, rdi; lpString2
0x180037015  call    ?FwAdvPolicyLookForSetID@@YAJPEAUHKEY__@@PEBGPEAK@Z; FwAdvPolicyLookForSetID(HKEY__ *,ushort const *,ulong *)
0x18003701a  mov     ebx, eax
0x18003701c  test    eax, eax
0x18003701e  jns     short loc_18003704B
0x180037020  mov     rcx, cs:WPP_GLOBAL_Control
0x180037027  lea     rdx, WPP_GLOBAL_Control
0x18003702e  cmp     rcx, rdx
0x180037031  jz      loc_18003717B
0x180037037  test    byte ptr [rcx+1Ch], 1
0x18003703b  jz      loc_18003717B
0x180037041  mov     edx, 42h ; 'B'
0x180037046  jmp     loc_180037168
0x18003704b  mov     eax, [rbp+var_38]
0x18003704e  cmp     eax, 1
0x180037051  jbe     short loc_180037086
0x180037053  mov     ebx, 8000FFFFh
0x180037058  mov     rcx, cs:WPP_GLOBAL_Control
0x18003705f  lea     rdx, WPP_GLOBAL_Control
0x180037066  cmp     rcx, rdx
0x180037069  jz      loc_18003717B
0x18003706f  test    byte ptr [rcx+1Ch], 1
0x180037073  jz      loc_18003717B
0x180037079  mov     edx, 43h ; 'C'
0x18003707e  mov     r9d, ebx
0x180037081  jmp     loc_18003716B
0x180037086  test    eax, eax
0x180037088  jnz     short loc_1800370BC
0x18003708a  mov     r9d, 80070002h
0x180037090  mov     ebx, r9d
0x180037093  mov     rcx, cs:WPP_GLOBAL_Control
0x18003709a  lea     rdx, WPP_GLOBAL_Control
0x1800370a1  cmp     rcx, rdx
0x1800370a4  jz      loc_18003717B
0x1800370aa  test    byte ptr [rcx+1Ch], 1
0x1800370ae  jz      loc_18003717B
0x1800370b4  lea     edx, [rax+44h]
0x1800370b7  jmp     loc_18003716B
0x1800370bc  mov     rcx, [rbp+hKey]
0x1800370c0  mov     rdx, rdi
0x1800370c3  call    cs:__imp_FwRegDeleteKey
0x1800370c9  mov     ebx, eax
0x1800370cb  test    eax, eax
0x1800370cd  jns     short loc_1800370F7
0x1800370cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370d6  lea     rdx, WPP_GLOBAL_Control
0x1800370dd  cmp     rcx, rdx
0x1800370e0  jz      loc_18003717B
0x1800370e6  test    byte ptr [rcx+1Ch], 1
0x1800370ea  jz      loc_18003717B
0x1800370f0  mov     edx, 45h ; 'E'
0x1800370f5  jmp     short loc_180037168
0x1800370f7  mov     rcx, [rbp+hKey]
0x1800370fb  lea     r9, [rbp+var_20]
0x1800370ff  mov     r8d, 0Fh
0x180037105  mov     rdx, rdi
0x180037108  call    cs:__imp_FwRegCreateKey
0x18003710e  mov     ebx, eax
0x180037110  test    eax, eax
0x180037112  jns     short loc_180037134
0x180037114  mov     rcx, cs:WPP_GLOBAL_Control
0x18003711b  lea     rdx, WPP_GLOBAL_Control
0x180037122  cmp     rcx, rdx
0x180037125  jz      short loc_18003717B
0x180037127  test    byte ptr [rcx+1Ch], 1
0x18003712b  jz      short loc_18003717B
0x18003712d  mov     edx, 46h ; 'F'
0x180037132  jmp     short loc_180037168
0x180037134  mov     rdx, [rbp+var_20]
0x180037138  mov     rcx, r14
0x18003713b  mov     rax, [rsi+58h]
0x18003713f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037144  mov     ebx, eax
0x180037146  test    eax, eax
0x180037148  jns     short loc_18003717B
0x18003714a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037151  lea     rdx, WPP_GLOBAL_Control
0x180037158  cmp     rcx, rdx
0x18003715b  jz      short loc_18003717B
0x18003715d  test    byte ptr [rcx+1Ch], 1
0x180037161  jz      short loc_18003717B
0x180037163  mov     edx, 47h ; 'G'
0x180037168  mov     r9d, eax
0x18003716b  mov     rcx, [rcx+10h]
0x18003716f  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x180037176  call    WPP_SF_d
0x18003717b  mov     rcx, [rbp+var_28]
0x18003717f  call    cs:__imp_FwFree
0x180037185  mov     rcx, [rbp+var_20]
0x180037189  call    cs:__imp_FwRegCloseKey
0x18003718f  mov     rcx, [rbp+hKey]
0x180037193  call    cs:__imp_FwRegCloseKey
0x180037199  mov     eax, ebx
0x18003719b  mov     rcx, [rbp+var_10]
0x18003719f  xor     rcx, rsp; StackCookie
0x1800371a2  call    __security_check_cookie
0x1800371a7  add     rsp, 68h
0x1800371ab  pop     r15
0x1800371ad  pop     r14
0x1800371af  pop     rdi
0x1800371b0  pop     rsi
0x1800371b1  pop     rbx
0x1800371b2  pop     rbp
0x1800371b3  retn
```
