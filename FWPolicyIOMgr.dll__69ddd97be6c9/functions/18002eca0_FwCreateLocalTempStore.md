# FwCreateLocalTempStore

- ea: `0x18002eca0`
- end: `0x18002ee74`
- name: `FwCreateLocalTempStore`
- size: `468`
- prototype: `__int64 __fastcall(__int64, void *, __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18002eca0`
- `0x18002f470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002edd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ede0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002edd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ede0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002ee0b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002ee0b`
- `fwbase!FwAlloc` at `0x18002ece9`
- `fwbase!FwAlloc` at `0x18002ece9`
- `fwbase!FwStringCopy` at `0x18002ed9d`
- `fwbase!FwStringCopy` at `0x18002ed9d`

## pseudocode

```c
__int64 __fastcall FwCreateLocalTempStore(__int64 a1, void *a2, __int64 *a3)
{
  __int64 v6; // rsi
  unsigned int v7; // edi
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 *v12; // rax
  _OWORD *v13; // rcx
  __int128 v14; // xmm1
  int v15; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 364, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v6 = FwAlloc(264);
  if ( !v6 )
  {
    v7 = -2147024882;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v9 = 365;
    v10 = 2147942414LL;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v10);
LABEL_22:
    FwDestroyLocalTempStore((struct _tag_WF_POLICY_STORE *)v6);
    return v7;
  }
  v11 = 2;
  v12 = qword_18004DAB0;
  v13 = (_OWORD *)v6;
  do
  {
    *v13 = *(_OWORD *)v12;
    v13[1] = *((_OWORD *)v12 + 1);
    v13[2] = *((_OWORD *)v12 + 2);
    v13[3] = *((_OWORD *)v12 + 3);
    v13[4] = *((_OWORD *)v12 + 4);
    v13[5] = *((_OWORD *)v12 + 5);
    v13[6] = *((_OWORD *)v12 + 6);
    v14 = *((_OWORD *)v12 + 7);
    v12 += 16;
    v13[7] = v14;
    v13 += 8;
    --v11;
  }
  while ( v11 );
  *(_QWORD *)v13 = *v12;
  v15 = FwStringCopy(a1, v6 + 16);
  v7 = v15;
  if ( v15 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v9 = 366;
    v10 = (unsigned int)v15;
    goto LABEL_8;
  }
  *(_DWORD *)(v6 + 4) = 1;
  CurrentProcess = GetCurrentProcess();
  v17 = GetCurrentProcess();
  if ( DuplicateHandle(v17, a2, CurrentProcess, (LPHANDLE)(v6 + 40), 0, 1, 2u) )
  {
    *a3 = v6;
    return v7;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 367, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v7);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_22;
  return v7;
}

```

## disassembly

```asm
0x18002eca0  push    rbx
0x18002eca2  push    rbp
0x18002eca3  push    rsi
0x18002eca4  push    rdi
0x18002eca5  push    r14
0x18002eca7  push    r15
0x18002eca9  sub     rsp, 48h
0x18002ecad  mov     r14, r8
0x18002ecb0  mov     rbp, rdx
0x18002ecb3  mov     rbx, rcx
0x18002ecb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecbd  lea     r15, WPP_GLOBAL_Control
0x18002ecc4  cmp     rcx, r15
0x18002ecc7  jz      short loc_18002ECE4
0x18002ecc9  test    byte ptr [rcx+1Ch], 8
0x18002eccd  jz      short loc_18002ECE4
0x18002eccf  mov     rcx, [rcx+10h]
0x18002ecd3  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002ecda  mov     edx, 16Ch
0x18002ecdf  call    WPP_SF_
0x18002ece4  mov     ecx, 108h
0x18002ece9  call    cs:__imp_FwAlloc
0x18002ecef  mov     rsi, rax
0x18002ecf2  test    rax, rax
0x18002ecf5  jnz     short loc_18002ED33
0x18002ecf7  mov     edi, 8007000Eh
0x18002ecfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed03  cmp     rcx, r15
0x18002ed06  jz      loc_18002EE58
0x18002ed0c  test    byte ptr [rcx+1Ch], 1
0x18002ed10  jz      loc_18002EE58
0x18002ed16  mov     edx, 16Dh
0x18002ed1b  mov     r9d, edi
0x18002ed1e  mov     rcx, [rcx+10h]
0x18002ed22  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002ed29  call    WPP_SF_d
0x18002ed2e  jmp     loc_18002EE58
0x18002ed33  mov     edx, 2
0x18002ed38  lea     rax, qword_18004DAB0
0x18002ed3f  mov     rcx, rsi
0x18002ed42  lea     r8d, [rdx+7Eh]
0x18002ed46  movups  xmm0, xmmword ptr [rax]
0x18002ed49  movups  xmmword ptr [rcx], xmm0
0x18002ed4c  movups  xmm1, xmmword ptr [rax+10h]
0x18002ed50  movups  xmmword ptr [rcx+10h], xmm1
0x18002ed54  movups  xmm0, xmmword ptr [rax+20h]
0x18002ed58  movups  xmmword ptr [rcx+20h], xmm0
0x18002ed5c  movups  xmm1, xmmword ptr [rax+30h]
0x18002ed60  movups  xmmword ptr [rcx+30h], xmm1
0x18002ed64  movups  xmm0, xmmword ptr [rax+40h]
0x18002ed68  movups  xmmword ptr [rcx+40h], xmm0
0x18002ed6c  movups  xmm1, xmmword ptr [rax+50h]
0x18002ed70  movups  xmmword ptr [rcx+50h], xmm1
0x18002ed74  movups  xmm0, xmmword ptr [rax+60h]
0x18002ed78  movups  xmmword ptr [rcx+60h], xmm0
0x18002ed7c  movups  xmm1, xmmword ptr [rax+70h]
0x18002ed80  add     rax, r8
0x18002ed83  movups  xmmword ptr [rcx+70h], xmm1
0x18002ed87  add     rcx, r8
0x18002ed8a  sub     rdx, 1
0x18002ed8e  jnz     short loc_18002ED46
0x18002ed90  mov     rax, [rax]
0x18002ed93  lea     rdx, [rsi+10h]
0x18002ed97  mov     [rcx], rax
0x18002ed9a  mov     rcx, rbx
0x18002ed9d  call    cs:__imp_FwStringCopy
0x18002eda3  mov     edi, eax
0x18002eda5  test    eax, eax
0x18002eda7  jns     short loc_18002EDD0
0x18002eda9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edb0  cmp     rcx, r15
0x18002edb3  jz      loc_18002EE58
0x18002edb9  test    byte ptr [rcx+1Ch], 1
0x18002edbd  jz      loc_18002EE58
0x18002edc3  mov     edx, 16Eh
0x18002edc8  mov     r9d, eax
0x18002edcb  jmp     loc_18002ED1E
0x18002edd0  mov     dword ptr [rsi+4], 1
0x18002edd7  call    cs:__imp_GetCurrentProcess
0x18002eddd  mov     rbx, rax
0x18002ede0  call    cs:__imp_GetCurrentProcess
0x18002ede6  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18002edee  lea     r9, [rsi+28h]; lpTargetHandle
0x18002edf2  mov     rcx, rax; hSourceProcessHandle
0x18002edf5  mov     [rsp+78h+bInheritHandle], 1; bInheritHandle
0x18002edfd  mov     r8, rbx; hTargetProcessHandle
0x18002ee00  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18002ee08  mov     rdx, rbp; hSourceHandle
0x18002ee0b  call    cs:__imp_DuplicateHandle
0x18002ee11  test    eax, eax
0x18002ee13  jnz     short loc_18002EE62
0x18002ee15  call    cs:__imp_GetLastError
0x18002ee1b  mov     edi, eax
0x18002ee1d  test    eax, eax
0x18002ee1f  jle     short loc_18002EE2A
0x18002ee21  movzx   edi, ax
0x18002ee24  or      edi, 80070000h
0x18002ee2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee31  cmp     rcx, r15
0x18002ee34  jz      short loc_18002EE54
0x18002ee36  test    byte ptr [rcx+1Ch], 1
0x18002ee3a  jz      short loc_18002EE54
0x18002ee3c  mov     rcx, [rcx+10h]
0x18002ee40  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002ee47  mov     edx, 16Fh
0x18002ee4c  mov     r9d, edi
0x18002ee4f  call    WPP_SF_d
0x18002ee54  test    edi, edi
0x18002ee56  jns     short loc_18002EE65
0x18002ee58  mov     rcx, rsi; struct _tag_WF_POLICY_STORE *
0x18002ee5b  call    FwDestroyLocalTempStore
0x18002ee60  jmp     short loc_18002EE65
0x18002ee62  mov     [r14], rsi
0x18002ee65  mov     eax, edi
0x18002ee67  add     rsp, 48h
0x18002ee6b  pop     r15
0x18002ee6d  pop     r14
0x18002ee6f  pop     rdi
0x18002ee70  pop     rsi
0x18002ee71  pop     rbp
0x18002ee72  pop     rbx
0x18002ee73  retn
```
