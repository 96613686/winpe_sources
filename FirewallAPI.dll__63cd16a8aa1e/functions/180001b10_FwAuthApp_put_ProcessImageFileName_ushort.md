# FwAuthApp::put_ProcessImageFileName(ushort *)

- ea: `0x180001b10`
- end: `0x180001dc8`
- name: `?put_ProcessImageFileName@FwAuthApp@@UEAAJPEAG@Z`
- size: `696`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, BSTR pbstr)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001b10`
- `0x180001dd0`
- `0x18000270c`
- `0x1800277b0`
- `0x1800284c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001b88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001b88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d72`
- `OLEAUT32!__imp_SysStringLen` at `0x180001b91`
- `OLEAUT32!__imp_SysStringLen` at `0x180001b91`
- `fwbase!FwBaseFree` at `0x180001d88`
- `fwbase!FwBaseFree` at `0x180001d88`
- `fwbase!FwImageListDestroy` at `0x180001d7d`
- `fwbase!FwImageListDestroy` at `0x180001d7d`
- `fwbase!FwImageListHasImage` at `0x180001be5`
- `fwbase!FwImageListHasImage` at `0x180001be5`
- `fwbase!FwGetAppBlockList` at `0x180001bcb`
- `fwbase!FwGetAppBlockList` at `0x180001bcb`
- `fwbase!FwGetSysPathName` at `0x180001bb6`
- `fwbase!FwGetSysPathName` at `0x180001bb6`
- `fwbase!FwReportReturnError` at `0x180001d68`
- `fwbase!FwReportReturnError` at `0x180001d97`
- `fwbase!FwReportReturnError` at `0x180001d68`
- `fwbase!FwReportReturnError` at `0x180001d97`

## pseudocode

```c
__int64 __fastcall FwAuthApp::put_ProcessImageFileName(FwAuthApp *this, BSTR pbstr)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int SysPathName; // eax
  _OWORD *v7; // rax
  _OWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int128 v11; // xmm1
  __int64 v12; // r9
  _OWORD *v13; // rdx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v18[3]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v19[272]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+150h] [rbp+50h]
  _BYTE v21[272]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v22; // [rsp+350h] [rbp+250h]

  v17 = 0;
  v18[0] = 0;
  v18[1] = 0;
  memset_0(v21, 0, 0x1F8u);
  memset_0(v19, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !SysStringLen(pbstr) )
  {
    v4 = -2147024809;
LABEL_3:
    v5 = v4;
LABEL_15:
    FwReportReturnError("FwAuthApp::put_ProcessImageFileName", v5);
    goto LABEL_16;
  }
  SysPathName = FwGetSysPathName(pbstr, &v17);
  v4 = SysPathName;
  if ( SysPathName < 0 )
    goto LABEL_14;
  SysPathName = FwGetAppBlockList(v18);
  v4 = SysPathName;
  if ( SysPathName < 0 )
    goto LABEL_14;
  if ( (unsigned int)FwImageListHasImage(v18, v17) )
  {
    v4 = -2147016473;
    goto LABEL_3;
  }
  SysPathName = FwAuthApp::CreateDefaultAuthAppRules(this);
  v4 = SysPathName;
  if ( SysPathName < 0 )
    goto LABEL_14;
  v7 = (_OWORD *)*((_QWORD *)this + 9);
  v8 = v21;
  v9 = 3;
  v10 = 3;
  do
  {
    *v8 = *v7;
    v8[1] = v7[1];
    v8[2] = v7[2];
    v8[3] = v7[3];
    v8[4] = v7[4];
    v8[5] = v7[5];
    v8[6] = v7[6];
    v11 = v7[7];
    v7 += 8;
    v8[7] = v11;
    v8 += 8;
    --v10;
  }
  while ( v10 );
  v12 = v17;
  v13 = v19;
  *v8 = *v7;
  v8[1] = v7[1];
  v8[2] = v7[2];
  v8[3] = v7[3];
  v8[4] = v7[4];
  v8[5] = v7[5];
  v8[6] = v7[6];
  *((_QWORD *)v8 + 14) = *((_QWORD *)v7 + 14);
  v14 = (_OWORD *)*((_QWORD *)this + 10);
  v22 = v12;
  do
  {
    *v13 = *v14;
    v13[1] = v14[1];
    v13[2] = v14[2];
    v13[3] = v14[3];
    v13[4] = v14[4];
    v13[5] = v14[5];
    v13[6] = v14[6];
    v15 = v14[7];
    v14 += 8;
    v13[7] = v15;
    v13 += 8;
    --v9;
  }
  while ( v9 );
  *v13 = *v14;
  v13[1] = v14[1];
  v13[2] = v14[2];
  v13[3] = v14[3];
  v13[4] = v14[4];
  v13[5] = v14[5];
  v13[6] = v14[6];
  *((_QWORD *)v13 + 14) = *((_QWORD *)v14 + 14);
  v20 = v12;
  SysPathName = FwAuthApp::SetRules(this, (const struct _tag_FW_RULE *)v21, (const struct _tag_FW_RULE *)v19);
  v4 = SysPathName;
  if ( SysPathName < 0 )
  {
LABEL_14:
    v5 = (unsigned int)SysPathName;
    goto LABEL_15;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwImageListDestroy(v18);
  FwBaseFree(v17);
  if ( (v4 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::put_ProcessImageFileName", v4);
  return v4;
}

```

## disassembly

```asm
0x180001b10  mov     [rsp-8+arg_10], rbx
0x180001b15  mov     [rsp-8+arg_18], rsi
0x180001b1a  push    rbp
0x180001b1b  push    rdi
0x180001b1c  push    r14
0x180001b1e  lea     rbp, [rsp-350h]
0x180001b26  sub     rsp, 450h
0x180001b2d  mov     rax, cs:__security_cookie
0x180001b34  xor     rax, rsp
0x180001b37  mov     [rbp+360h+var_20], rax
0x180001b3e  mov     rbx, rdx
0x180001b41  mov     [rsp+460h+var_440], 0
0x180001b4a  mov     rdi, rcx
0x180001b4d  mov     [rsp+460h+var_438], 0
0x180001b56  mov     esi, 1F8h
0x180001b5b  mov     [rsp+460h+var_430], 0
0x180001b64  mov     r8d, esi; Size
0x180001b67  lea     rcx, [rbp+360h+var_220]; void *
0x180001b6e  xor     edx, edx; Val
0x180001b70  call    memset_0
0x180001b75  mov     r8d, esi; Size
0x180001b78  lea     rcx, [rsp+460h+var_420]; void *
0x180001b7d  xor     edx, edx; Val
0x180001b7f  call    memset_0
0x180001b84  lea     rcx, [rdi+10h]; lpCriticalSection
0x180001b88  call    cs:__imp_EnterCriticalSection
0x180001b8e  mov     rcx, rbx; pbstr
0x180001b91  call    cs:__imp_SysStringLen
0x180001b97  lea     r14, aFwauthappPutPr; "FwAuthApp::put_ProcessImageFileName"
0x180001b9e  test    eax, eax
0x180001ba0  jnz     short loc_180001BAE
0x180001ba2  mov     ebx, 80070057h
0x180001ba7  mov     edx, ebx
0x180001ba9  jmp     loc_180001D65
0x180001bae  lea     rdx, [rsp+460h+var_440]
0x180001bb3  mov     rcx, rbx
0x180001bb6  call    cs:__imp_FwGetSysPathName
0x180001bbc  mov     ebx, eax
0x180001bbe  test    eax, eax
0x180001bc0  js      loc_180001D63
0x180001bc6  lea     rcx, [rsp+460h+var_438]
0x180001bcb  call    cs:__imp_FwGetAppBlockList
0x180001bd1  mov     ebx, eax
0x180001bd3  test    eax, eax
0x180001bd5  js      loc_180001D63
0x180001bdb  mov     rdx, [rsp+460h+var_440]
0x180001be0  lea     rcx, [rsp+460h+var_438]
0x180001be5  call    cs:__imp_FwImageListHasImage
0x180001beb  test    eax, eax
0x180001bed  jz      short loc_180001BF6
0x180001bef  mov     ebx, 800720E7h
0x180001bf4  jmp     short loc_180001BA7
0x180001bf6  mov     rcx, rdi; this
0x180001bf9  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x180001bfe  mov     ebx, eax
0x180001c00  test    eax, eax
0x180001c02  js      loc_180001D63
0x180001c08  mov     rax, [rdi+48h]
0x180001c0c  lea     rcx, [rbp+360h+var_220]
0x180001c13  mov     r8d, 3
0x180001c19  mov     edx, r8d
0x180001c1c  lea     r10d, [r8+7Dh]
0x180001c20  movups  xmm0, xmmword ptr [rax]
0x180001c23  movups  xmmword ptr [rcx], xmm0
0x180001c26  movups  xmm1, xmmword ptr [rax+10h]
0x180001c2a  movups  xmmword ptr [rcx+10h], xmm1
0x180001c2e  movups  xmm0, xmmword ptr [rax+20h]
0x180001c32  movups  xmmword ptr [rcx+20h], xmm0
0x180001c36  movups  xmm1, xmmword ptr [rax+30h]
0x180001c3a  movups  xmmword ptr [rcx+30h], xmm1
0x180001c3e  movups  xmm0, xmmword ptr [rax+40h]
0x180001c42  movups  xmmword ptr [rcx+40h], xmm0
0x180001c46  movups  xmm1, xmmword ptr [rax+50h]
0x180001c4a  movups  xmmword ptr [rcx+50h], xmm1
0x180001c4e  movups  xmm0, xmmword ptr [rax+60h]
0x180001c52  movups  xmmword ptr [rcx+60h], xmm0
0x180001c56  movups  xmm1, xmmword ptr [rax+70h]
0x180001c5a  add     rax, r10
0x180001c5d  movups  xmmword ptr [rcx+70h], xmm1
0x180001c61  add     rcx, r10
0x180001c64  sub     rdx, 1
0x180001c68  jnz     short loc_180001C20
0x180001c6a  movups  xmm0, xmmword ptr [rax]
0x180001c6d  mov     r9, [rsp+460h+var_440]
0x180001c72  lea     rdx, [rsp+460h+var_420]
0x180001c77  movups  xmmword ptr [rcx], xmm0
0x180001c7a  movups  xmm1, xmmword ptr [rax+10h]
0x180001c7e  movups  xmmword ptr [rcx+10h], xmm1
0x180001c82  movups  xmm0, xmmword ptr [rax+20h]
0x180001c86  movups  xmmword ptr [rcx+20h], xmm0
0x180001c8a  movups  xmm1, xmmword ptr [rax+30h]
0x180001c8e  movups  xmmword ptr [rcx+30h], xmm1
0x180001c92  movups  xmm0, xmmword ptr [rax+40h]
0x180001c96  movups  xmmword ptr [rcx+40h], xmm0
0x180001c9a  movups  xmm1, xmmword ptr [rax+50h]
0x180001c9e  movups  xmmword ptr [rcx+50h], xmm1
0x180001ca2  movups  xmm0, xmmword ptr [rax+60h]
0x180001ca6  movups  xmmword ptr [rcx+60h], xmm0
0x180001caa  mov     rax, [rax+70h]
0x180001cae  mov     [rcx+70h], rax
0x180001cb2  mov     rax, [rdi+50h]
0x180001cb6  mov     [rbp+360h+var_110], r9
0x180001cbd  movups  xmm0, xmmword ptr [rax]
0x180001cc0  movups  xmmword ptr [rdx], xmm0
0x180001cc3  movups  xmm1, xmmword ptr [rax+10h]
0x180001cc7  movups  xmmword ptr [rdx+10h], xmm1
0x180001ccb  movups  xmm0, xmmword ptr [rax+20h]
0x180001ccf  movups  xmmword ptr [rdx+20h], xmm0
0x180001cd3  movups  xmm1, xmmword ptr [rax+30h]
0x180001cd7  movups  xmmword ptr [rdx+30h], xmm1
0x180001cdb  movups  xmm0, xmmword ptr [rax+40h]
0x180001cdf  movups  xmmword ptr [rdx+40h], xmm0
0x180001ce3  movups  xmm1, xmmword ptr [rax+50h]
0x180001ce7  movups  xmmword ptr [rdx+50h], xmm1
0x180001ceb  movups  xmm0, xmmword ptr [rax+60h]
0x180001cef  movups  xmmword ptr [rdx+60h], xmm0
0x180001cf3  movups  xmm1, xmmword ptr [rax+70h]
0x180001cf7  add     rax, r10
0x180001cfa  movups  xmmword ptr [rdx+70h], xmm1
0x180001cfe  add     rdx, r10
0x180001d01  sub     r8, 1
0x180001d05  jnz     short loc_180001CBD
0x180001d07  movups  xmm0, xmmword ptr [rax]
0x180001d0a  lea     r8, [rsp+460h+var_420]; struct _tag_FW_RULE *
0x180001d0f  mov     rcx, rdi; this
0x180001d12  movups  xmmword ptr [rdx], xmm0
0x180001d15  movups  xmm1, xmmword ptr [rax+10h]
0x180001d19  movups  xmmword ptr [rdx+10h], xmm1
0x180001d1d  movups  xmm0, xmmword ptr [rax+20h]
0x180001d21  movups  xmmword ptr [rdx+20h], xmm0
0x180001d25  movups  xmm1, xmmword ptr [rax+30h]
0x180001d29  movups  xmmword ptr [rdx+30h], xmm1
0x180001d2d  movups  xmm0, xmmword ptr [rax+40h]
0x180001d31  movups  xmmword ptr [rdx+40h], xmm0
0x180001d35  movups  xmm1, xmmword ptr [rax+50h]
0x180001d39  movups  xmmword ptr [rdx+50h], xmm1
0x180001d3d  movups  xmm0, xmmword ptr [rax+60h]
0x180001d41  movups  xmmword ptr [rdx+60h], xmm0
0x180001d45  mov     rax, [rax+70h]
0x180001d49  mov     [rdx+70h], rax
0x180001d4d  lea     rdx, [rbp+360h+var_220]; struct _tag_FW_RULE *
0x180001d54  mov     [rbp+360h+var_310], r9
0x180001d58  call    ?SetRules@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@0@Z; FwAuthApp::SetRules(_tag_FW_RULE const *,_tag_FW_RULE const *)
0x180001d5d  mov     ebx, eax
0x180001d5f  test    eax, eax
0x180001d61  jns     short loc_180001D6E
0x180001d63  mov     edx, eax
0x180001d65  mov     rcx, r14
0x180001d68  call    cs:__imp_FwReportReturnError
0x180001d6e  lea     rcx, [rdi+10h]; lpCriticalSection
0x180001d72  call    cs:__imp_LeaveCriticalSection
0x180001d78  lea     rcx, [rsp+460h+var_438]
0x180001d7d  call    cs:__imp_FwImageListDestroy
0x180001d83  mov     rcx, [rsp+460h+var_440]
0x180001d88  call    cs:__imp_FwBaseFree
0x180001d8e  test    ebx, ebx
0x180001d90  jns     short loc_180001D9F
0x180001d92  mov     edx, ebx
0x180001d94  mov     rcx, r14
0x180001d97  call    cs:__imp_FwReportReturnError
0x180001d9d  mov     ebx, eax
0x180001d9f  mov     eax, ebx
0x180001da1  mov     rcx, [rbp+360h+var_20]
0x180001da8  xor     rcx, rsp; StackCookie
0x180001dab  call    __security_check_cookie
0x180001db0  lea     r11, [rsp+460h+var_10]
0x180001db8  mov     rbx, [r11+30h]
0x180001dbc  mov     rsi, [r11+38h]
0x180001dc0  mov     rsp, r11
0x180001dc3  pop     r14
0x180001dc5  pop     rdi
0x180001dc6  pop     rbp
0x180001dc7  retn
```
