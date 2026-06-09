# FwAdvPolicyAddSet(_tag_FW_SET_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE *,ushort const *)

- ea: `0x1800367d0`
- end: `0x180036b54`
- name: `?FwAdvPolicyAddSet@@YAJPEAU_tag_FW_SET_MANIPULATOR@@PEAUHKEY__@@PEBGPEAU_tag_FW_BLOB_RULE@@2@Z`
- size: `900`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *), HKEY, const unsigned __int16 *, struct _tag_FW_BLOB_RULE *, LPCWSTR lpString1)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eb30`

## callees

- `0x1800042c4`
- `0x18001e9ac`
- `0x18001ec98`
- `0x18001f650`
- `0x18001ffd4`
- `0x1800367d0`
- `0x180036d3c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800368de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800368de`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180036913`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180036913`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180036956`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180036956`
- `fwbase!FwFree` at `0x180036b1c`
- `fwbase!FwFree` at `0x180036b1c`
- `fwbase!FwStringBuild` at `0x18003699f`
- `fwbase!FwStringBuild` at `0x18003699f`
- `fwbase!FwRegCloseKey` at `0x180036b26`
- `fwbase!FwRegCloseKey` at `0x180036b30`
- `fwbase!FwRegCloseKey` at `0x180036b26`
- `fwbase!FwRegCloseKey` at `0x180036b30`
- `fwbase!FwRegCreateKey` at `0x18003683c`
- `fwbase!FwRegCreateKey` at `0x180036aa5`
- `fwbase!FwRegCreateKey` at `0x18003683c`
- `fwbase!FwRegCreateKey` at `0x180036aa5`
- `fwbase!FwRegSetString` at `0x1800369e6`
- `fwbase!FwRegSetString` at `0x1800369e6`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyAddSet(
        __int64 (__fastcall **a1)(struct _tag_FW_BLOB_RULE *),
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_FW_BLOB_RULE *a4,
        LPCWSTR lpString1)
{
  HRESULT MergedGPODefaultID; // eax
  unsigned int v10; // ebx
  LPCOLESTR v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rdi
  LPCWSTR *v14; // rax
  __int64 v15; // r9
  unsigned int v17; // [rsp+20h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-69h] BYREF
  unsigned __int16 *v19; // [rsp+30h] [rbp-61h] BYREF
  __int64 v20; // [rsp+38h] [rbp-59h] BYREF
  GUID pguid; // [rsp+40h] [rbp-51h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-41h] BYREF

  hKey = 0;
  v20 = 0;
  v17 = 0;
  v19 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  MergedGPODefaultID = FwRegCreateKey(a2, a3, 15, &hKey);
  v10 = MergedGPODefaultID;
  if ( MergedGPODefaultID < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 53;
LABEL_47:
      v15 = (unsigned int)MergedGPODefaultID;
      goto LABEL_48;
    }
    goto LABEL_49;
  }
  MergedGPODefaultID = FwGetMergedGPODefaultID(hKey, lpString1, &v19);
  v10 = MergedGPODefaultID;
  if ( MergedGPODefaultID >= 0 )
  {
    v13 = *(unsigned __int16 **)a1[6](a4);
    if ( lpString1 )
    {
      v14 = (LPCWSTR *)a1[6](a4);
      if ( !lstrcmpiW(lpString1, *v14) )
      {
        v13 = v19;
        if ( !v19 )
        {
          pguid = 0;
          memset_0(sz, 0, 0x4Eu);
          MergedGPODefaultID = CoCreateGuid(&pguid);
          v10 = MergedGPODefaultID;
          if ( MergedGPODefaultID < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v12 = 55;
              goto LABEL_47;
            }
            goto LABEL_49;
          }
          if ( !StringFromGUID2(&pguid, sz, 39) )
          {
            v10 = -2147024774;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_49;
            v12 = 56;
            goto LABEL_22;
          }
          MergedGPODefaultID = FwStringBuild(&v19, lpString1, sz, 0);
          v10 = MergedGPODefaultID;
          if ( MergedGPODefaultID < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v12 = 57;
              goto LABEL_47;
            }
            goto LABEL_49;
          }
          v13 = v19;
          MergedGPODefaultID = FwRegSetString(hKey, 0, lpString1, v19);
          v10 = MergedGPODefaultID;
          if ( MergedGPODefaultID < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v12 = 58;
              goto LABEL_47;
            }
            goto LABEL_49;
          }
        }
      }
    }
    MergedGPODefaultID = FwAdvPolicyLookForSetID(hKey, v13, &v17);
    v10 = MergedGPODefaultID;
    if ( MergedGPODefaultID < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 59;
        goto LABEL_47;
      }
      goto LABEL_49;
    }
    if ( !v17 )
    {
      MergedGPODefaultID = FwRegCreateKey(hKey, v13, 15, &v20);
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
            v12 = 62;
            goto LABEL_47;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 61;
          goto LABEL_47;
        }
      }
      goto LABEL_49;
    }
    v10 = -2147418113;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_49;
    v12 = 60;
LABEL_22:
    v15 = v10;
LABEL_48:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v15);
    goto LABEL_49;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = 54;
    goto LABEL_47;
  }
LABEL_49:
  FwFree(v19);
  FwRegCloseKey(v20);
  FwRegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1800367d0  push    rbp
0x1800367d2  push    rbx
0x1800367d3  push    rsi
0x1800367d4  push    rdi
0x1800367d5  push    r14
0x1800367d7  push    r15
0x1800367d9  lea     rbp, [rsp-27h]
0x1800367de  sub     rsp, 0B8h
0x1800367e5  mov     rax, cs:__security_cookie
0x1800367ec  xor     rax, rsp
0x1800367ef  mov     [rbp+4Fh+var_40], rax
0x1800367f3  mov     rsi, [rbp+4Fh+lpString1]
0x1800367f7  mov     r15, r9
0x1800367fa  mov     [rbp+4Fh+hKey], 0
0x180036802  mov     rdi, r8
0x180036805  mov     [rbp+4Fh+var_A8], 0
0x18003680d  mov     rbx, rdx
0x180036810  mov     [rbp+4Fh+var_C0], 0
0x180036817  mov     r14, rcx
0x18003681a  mov     [rbp+4Fh+var_B0], 0
0x180036822  test    rdx, rdx
0x180036825  jnz     short loc_18003682C
0x180036827  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003682c  lea     r9, [rbp+4Fh+hKey]
0x180036830  mov     r8d, 0Fh
0x180036836  mov     rdx, rdi
0x180036839  mov     rcx, rbx
0x18003683c  call    cs:__imp_FwRegCreateKey
0x180036842  mov     ebx, eax
0x180036844  test    eax, eax
0x180036846  jns     short loc_180036873
0x180036848  mov     rcx, cs:WPP_GLOBAL_Control
0x18003684f  lea     rdx, WPP_GLOBAL_Control
0x180036856  cmp     rcx, rdx
0x180036859  jz      loc_180036B18
0x18003685f  test    byte ptr [rcx+1Ch], 1
0x180036863  jz      loc_180036B18
0x180036869  mov     edx, 35h ; '5'
0x18003686e  jmp     loc_180036B05
0x180036873  mov     rcx, [rbp+4Fh+hKey]; HKEY
0x180036877  lea     r8, [rbp+4Fh+var_B0]; unsigned __int16 **
0x18003687b  mov     rdx, rsi; unsigned __int16 *
0x18003687e  call    ?FwGetMergedGPODefaultID@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; FwGetMergedGPODefaultID(HKEY__ *,ushort const *,ushort * *)
0x180036883  mov     ebx, eax
0x180036885  test    eax, eax
0x180036887  jns     short loc_1800368B4
0x180036889  mov     rcx, cs:WPP_GLOBAL_Control
0x180036890  lea     rdx, WPP_GLOBAL_Control
0x180036897  cmp     rcx, rdx
0x18003689a  jz      loc_180036B18
0x1800368a0  test    byte ptr [rcx+1Ch], 1
0x1800368a4  jz      loc_180036B18
0x1800368aa  mov     edx, 36h ; '6'
0x1800368af  jmp     loc_180036B05
0x1800368b4  mov     rax, [r14+30h]
0x1800368b8  mov     rcx, r15
0x1800368bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368c0  mov     rdi, [rax]
0x1800368c3  test    rsi, rsi
0x1800368c6  jz      loc_180036A1D
0x1800368cc  mov     rax, [r14+30h]
0x1800368d0  mov     rcx, r15
0x1800368d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368d8  mov     rcx, rsi; lpString1
0x1800368db  mov     rdx, [rax]; lpString2
0x1800368de  call    cs:__imp_lstrcmpiW
0x1800368e4  test    eax, eax
0x1800368e6  jnz     loc_180036A1D
0x1800368ec  mov     rdi, [rbp+4Fh+var_B0]
0x1800368f0  test    rdi, rdi
0x1800368f3  jnz     loc_180036A1D
0x1800368f9  xorps   xmm0, xmm0
0x1800368fc  lea     r8d, [rax+4Eh]; Size
0x180036900  xor     edx, edx; Val
0x180036902  lea     rcx, [rbp+4Fh+sz]; void *
0x180036906  movups  xmmword ptr [rbp+4Fh+pguid.Data1], xmm0
0x18003690a  call    memset_0
0x18003690f  lea     rcx, [rbp+4Fh+pguid]; pguid
0x180036913  call    cs:__imp_CoCreateGuid
0x180036919  mov     ebx, eax
0x18003691b  test    eax, eax
0x18003691d  jns     short loc_180036948
0x18003691f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036926  lea     rdx, WPP_GLOBAL_Control
0x18003692d  cmp     rcx, rdx
0x180036930  jz      loc_180036B18
0x180036936  test    byte ptr [rcx+1Ch], 1
0x18003693a  jz      loc_180036B18
0x180036940  lea     edx, [rdi+37h]
0x180036943  jmp     loc_180036B05
0x180036948  mov     r8d, 27h ; '''; cchMax
0x18003694e  lea     rdx, [rbp+4Fh+sz]; lpsz
0x180036952  lea     rcx, [rbp+4Fh+pguid]; rguid
0x180036956  call    cs:__imp_StringFromGUID2
0x18003695c  test    eax, eax
0x18003695e  jnz     short loc_180036991
0x180036960  mov     ebx, 8007007Ah
0x180036965  mov     rcx, cs:WPP_GLOBAL_Control
0x18003696c  lea     rdx, WPP_GLOBAL_Control
0x180036973  cmp     rcx, rdx
0x180036976  jz      loc_180036B18
0x18003697c  test    byte ptr [rcx+1Ch], 1
0x180036980  jz      loc_180036B18
0x180036986  lea     edx, [rax+38h]
0x180036989  mov     r9d, ebx
0x18003698c  jmp     loc_180036B08
0x180036991  xor     r9d, r9d
0x180036994  lea     r8, [rbp+4Fh+sz]
0x180036998  mov     rdx, rsi
0x18003699b  lea     rcx, [rbp+4Fh+var_B0]
0x18003699f  call    cs:__imp_FwStringBuild
0x1800369a5  mov     ebx, eax
0x1800369a7  test    eax, eax
0x1800369a9  jns     short loc_1800369D6
0x1800369ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369b2  lea     rdx, WPP_GLOBAL_Control
0x1800369b9  cmp     rcx, rdx
0x1800369bc  jz      loc_180036B18
0x1800369c2  test    byte ptr [rcx+1Ch], 1
0x1800369c6  jz      loc_180036B18
0x1800369cc  mov     edx, 39h ; '9'
0x1800369d1  jmp     loc_180036B05
0x1800369d6  mov     rdi, [rbp+4Fh+var_B0]
0x1800369da  mov     r8, rsi
0x1800369dd  mov     rcx, [rbp+4Fh+hKey]
0x1800369e1  mov     r9, rdi
0x1800369e4  xor     edx, edx
0x1800369e6  call    cs:__imp_FwRegSetString
0x1800369ec  mov     ebx, eax
0x1800369ee  test    eax, eax
0x1800369f0  jns     short loc_180036A1D
0x1800369f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369f9  lea     rdx, WPP_GLOBAL_Control
0x180036a00  cmp     rcx, rdx
0x180036a03  jz      loc_180036B18
0x180036a09  test    byte ptr [rcx+1Ch], 1
0x180036a0d  jz      loc_180036B18
0x180036a13  mov     edx, 3Ah ; ':'
0x180036a18  jmp     loc_180036B05
0x180036a1d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180036a21  lea     r8, [rbp+4Fh+var_C0]; unsigned int *
0x180036a25  mov     rdx, rdi; lpString2
0x180036a28  call    ?FwAdvPolicyLookForSetID@@YAJPEAUHKEY__@@PEBGPEAK@Z; FwAdvPolicyLookForSetID(HKEY__ *,ushort const *,ulong *)
0x180036a2d  mov     ebx, eax
0x180036a2f  test    eax, eax
0x180036a31  jns     short loc_180036A5E
0x180036a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a3a  lea     rdx, WPP_GLOBAL_Control
0x180036a41  cmp     rcx, rdx
0x180036a44  jz      loc_180036B18
0x180036a4a  test    byte ptr [rcx+1Ch], 1
0x180036a4e  jz      loc_180036B18
0x180036a54  mov     edx, 3Bh ; ';'
0x180036a59  jmp     loc_180036B05
0x180036a5e  cmp     [rbp+4Fh+var_C0], 0
0x180036a62  jbe     short loc_180036A94
0x180036a64  mov     ebx, 8000FFFFh
0x180036a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a70  lea     rdx, WPP_GLOBAL_Control
0x180036a77  cmp     rcx, rdx
0x180036a7a  jz      loc_180036B18
0x180036a80  test    byte ptr [rcx+1Ch], 1
0x180036a84  jz      loc_180036B18
0x180036a8a  mov     edx, 3Ch ; '<'
0x180036a8f  jmp     loc_180036989
0x180036a94  mov     rcx, [rbp+4Fh+hKey]
0x180036a98  lea     r9, [rbp+4Fh+var_A8]
0x180036a9c  mov     r8d, 0Fh
0x180036aa2  mov     rdx, rdi
0x180036aa5  call    cs:__imp_FwRegCreateKey
0x180036aab  mov     ebx, eax
0x180036aad  test    eax, eax
0x180036aaf  jns     short loc_180036AD1
0x180036ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ab8  lea     rdx, WPP_GLOBAL_Control
0x180036abf  cmp     rcx, rdx
0x180036ac2  jz      short loc_180036B18
0x180036ac4  test    byte ptr [rcx+1Ch], 1
0x180036ac8  jz      short loc_180036B18
0x180036aca  mov     edx, 3Dh ; '='
0x180036acf  jmp     short loc_180036B05
0x180036ad1  mov     rdx, [rbp+4Fh+var_A8]
0x180036ad5  mov     rcx, r15
0x180036ad8  mov     rax, [r14+58h]
0x180036adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ae1  mov     ebx, eax
0x180036ae3  test    eax, eax
0x180036ae5  jns     short loc_180036B18
0x180036ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036aee  lea     rdx, WPP_GLOBAL_Control
0x180036af5  cmp     rcx, rdx
0x180036af8  jz      short loc_180036B18
0x180036afa  test    byte ptr [rcx+1Ch], 1
0x180036afe  jz      short loc_180036B18
0x180036b00  mov     edx, 3Eh ; '>'
0x180036b05  mov     r9d, eax
0x180036b08  mov     rcx, [rcx+10h]
0x180036b0c  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x180036b13  call    WPP_SF_d
0x180036b18  mov     rcx, [rbp+4Fh+var_B0]
0x180036b1c  call    cs:__imp_FwFree
0x180036b22  mov     rcx, [rbp+4Fh+var_A8]
0x180036b26  call    cs:__imp_FwRegCloseKey
0x180036b2c  mov     rcx, [rbp+4Fh+hKey]
0x180036b30  call    cs:__imp_FwRegCloseKey
0x180036b36  mov     eax, ebx
0x180036b38  mov     rcx, [rbp+4Fh+var_40]
0x180036b3c  xor     rcx, rsp; StackCookie
0x180036b3f  call    __security_check_cookie
0x180036b44  add     rsp, 0B8h
0x180036b4b  pop     r15
0x180036b4d  pop     r14
0x180036b4f  pop     rdi
0x180036b50  pop     rsi
0x180036b51  pop     rbx
0x180036b52  pop     rbp
0x180036b53  retn
```
