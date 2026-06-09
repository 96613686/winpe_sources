# GetRepPath(ushort * const,ushort *)

- ea: `0x180013ffc`
- end: `0x1800142b7`
- name: `?GetRepPath@@YAJQEAGPEAG@Z`
- size: `699`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dcdc`

## callees

- `0x180004c30`
- `0x180012c34`
- `0x180013ffc`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001404c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001404c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014294`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800140f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800140f3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800141a8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800141a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014066`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001410d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001415f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800141c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001421c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014066`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001410d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001415f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800141c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001421c`
- `wbemcomn!GetMemLogObject` at `0x180014056`
- `wbemcomn!GetMemLogObject` at `0x1800140fd`
- `wbemcomn!GetMemLogObject` at `0x18001414f`
- `wbemcomn!GetMemLogObject` at `0x1800141b2`
- `wbemcomn!GetMemLogObject` at `0x18001420c`
- `wbemcomn!GetMemLogObject` at `0x180014056`
- `wbemcomn!GetMemLogObject` at `0x1800140fd`
- `wbemcomn!GetMemLogObject` at `0x18001414f`
- `wbemcomn!GetMemLogObject` at `0x1800141b2`
- `wbemcomn!GetMemLogObject` at `0x18001420c`

## string_xrefs

- `0x1800140e7`: `Repository Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRepPath(unsigned __int16 *const a1, unsigned __int16 *a2)
{
  CMemoryLog *v3; // rax
  unsigned int v4; // edi
  HKEY v5; // rbx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  __int64 v11; // rax
  CMemoryLog *v12; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey[0] = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, hKey) )
  {
    v5 = hKey[0];
    hKey[1] = hKey[0];
    cbData = 522;
    Type = 0;
    if ( RegQueryValueExW(hKey[0], L"Repository Directory", 0, &Type, (LPBYTE)Data, &cbData) )
    {
      MemLogObject = GetMemLogObject();
      v4 = -2147217407;
      CMemoryLog::Write(MemLogObject, -2147217407);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v8 = 49;
    }
    else if ( Type == 2 )
    {
      if ( ExpandEnvironmentStringsW(Data, a1, 0x105u) )
      {
        v11 = -1;
        do
          ++v11;
        while ( a1[v11] );
        if ( (unsigned int)v11 >= 2 )
        {
          if ( a1[(unsigned int)(v11 - 1)] != 92 )
            StringCchCatW(a1, 0x105u, L"\\");
          StringCchCatW(a1, 0x105u, L"repdrvfs.rec");
          v4 = 0;
          goto LABEL_32;
        }
        v12 = GetMemLogObject();
        v4 = -2147217407;
        CMemoryLog::Write(v12, -2147217407);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_32:
          RegCloseKey(v5);
          return v4;
        }
        v8 = 52;
      }
      else
      {
        v10 = GetMemLogObject();
        v4 = -2147217407;
        CMemoryLog::Write(v10, -2147217407);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_32;
        }
        v8 = 51;
      }
    }
    else
    {
      v9 = GetMemLogObject();
      v4 = -2147217407;
      CMemoryLog::Write(v9, -2147217407);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v8 = 50;
    }
    WPP_SF_d(v7[2], v8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749889LL);
    goto LABEL_32;
  }
  v3 = GetMemLogObject();
  v4 = -2147217407;
  CMemoryLog::Write(v3, -2147217407);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749889LL);
  }
  return v4;
}

```

## disassembly

```asm
0x180013ffc  push    rbp
0x180013ffe  push    rbx
0x180013fff  push    rsi
0x180014000  push    rdi
0x180014001  lea     rbp, [rsp-178h]
0x180014009  sub     rsp, 278h
0x180014010  mov     rax, cs:__security_cookie
0x180014017  xor     rax, rsp
0x18001401a  mov     [rbp+190h+var_30], rax
0x180014021  mov     rdi, rcx
0x180014024  xor     esi, esi
0x180014026  mov     [rsp+290h+hKey], rsi
0x18001402b  lea     rax, [rsp+290h+hKey]
0x180014030  mov     [rsp+290h+phkResult], rax; phkResult
0x180014035  mov     r9d, 20019h; samDesired
0x18001403b  xor     r8d, r8d; ulOptions
0x18001403e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x180014045  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001404c  call    cs:__imp_RegOpenKeyExW
0x180014052  test    eax, eax
0x180014054  jz      short loc_1800140B5
0x180014056  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001405c  mov     edi, 80041001h
0x180014061  mov     edx, edi
0x180014063  mov     rcx, rax
0x180014066  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001406c  lea     rax, WPP_GLOBAL_Control
0x180014073  mov     rcx, cs:WPP_GLOBAL_Control
0x18001407a  cmp     rcx, rax
0x18001407d  jz      loc_18001429A
0x180014083  test    byte ptr [rcx+1Ch], 1
0x180014087  jz      loc_18001429A
0x18001408d  cmp     byte ptr [rcx+19h], 2
0x180014091  jb      loc_18001429A
0x180014097  lea     edx, [rsi+30h]
0x18001409a  mov     r9d, 80041001h
0x1800140a0  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x1800140a7  mov     rcx, [rcx+10h]
0x1800140ab  call    WPP_SF_d
0x1800140b0  jmp     loc_18001429A
0x1800140b5  mov     rbx, [rsp+290h+hKey]
0x1800140ba  mov     [rsp+290h+var_250], rbx
0x1800140bf  mov     [rsp+290h+cbData], 20Ah
0x1800140c7  mov     [rsp+290h+Type], esi
0x1800140cb  lea     rax, [rsp+290h+cbData]
0x1800140d0  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800140d5  lea     rax, [rsp+290h+Data]
0x1800140da  mov     [rsp+290h+phkResult], rax; lpData
0x1800140df  lea     r9, [rsp+290h+Type]; lpType
0x1800140e4  xor     r8d, r8d; lpReserved
0x1800140e7  lea     rdx, aRepositoryDire; "Repository Directory"
0x1800140ee  mov     rcx, [rsp+290h+hKey]; hKey
0x1800140f3  call    cs:__imp_RegQueryValueExW
0x1800140f9  test    eax, eax
0x1800140fb  jz      short loc_180014148
0x1800140fd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014103  mov     edi, 80041001h
0x180014108  mov     edx, edi
0x18001410a  mov     rcx, rax
0x18001410d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014113  lea     rax, WPP_GLOBAL_Control
0x18001411a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014121  cmp     rcx, rax
0x180014124  jz      loc_180014291
0x18001412a  test    byte ptr [rcx+1Ch], 1
0x18001412e  jz      loc_180014291
0x180014134  cmp     byte ptr [rcx+19h], 2
0x180014138  jb      loc_180014291
0x18001413e  mov     edx, 31h ; '1'
0x180014143  jmp     loc_180014246
0x180014148  cmp     [rsp+290h+Type], 2
0x18001414d  jz      short loc_18001419A
0x18001414f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014155  mov     edi, 80041001h
0x18001415a  mov     edx, edi
0x18001415c  mov     rcx, rax
0x18001415f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014165  lea     rax, WPP_GLOBAL_Control
0x18001416c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014173  cmp     rcx, rax
0x180014176  jz      loc_180014291
0x18001417c  test    byte ptr [rcx+1Ch], 1
0x180014180  jz      loc_180014291
0x180014186  cmp     byte ptr [rcx+19h], 2
0x18001418a  jb      loc_180014291
0x180014190  mov     edx, 32h ; '2'
0x180014195  jmp     loc_180014246
0x18001419a  mov     r8d, 105h; nSize
0x1800141a0  mov     rdx, rdi; lpDst
0x1800141a3  lea     rcx, [rsp+290h+Data]; lpSrc
0x1800141a8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800141ae  test    eax, eax
0x1800141b0  jnz     short loc_1800141FA
0x1800141b2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800141b8  mov     edi, 80041001h
0x1800141bd  mov     edx, edi
0x1800141bf  mov     rcx, rax
0x1800141c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800141c8  lea     rax, WPP_GLOBAL_Control
0x1800141cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141d6  cmp     rcx, rax
0x1800141d9  jz      loc_180014291
0x1800141df  test    byte ptr [rcx+1Ch], 1
0x1800141e3  jz      loc_180014291
0x1800141e9  cmp     byte ptr [rcx+19h], 2
0x1800141ed  jb      loc_180014291
0x1800141f3  mov     edx, 33h ; '3'
0x1800141f8  jmp     short loc_180014246
0x1800141fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800141fe  inc     rax
0x180014201  cmp     [rdi+rax*2], si
0x180014205  jnz     short loc_1800141FE
0x180014207  cmp     eax, 2
0x18001420a  jnb     short loc_18001425E
0x18001420c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014212  mov     edi, 80041001h
0x180014217  mov     edx, edi
0x180014219  mov     rcx, rax
0x18001421c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014222  lea     rax, WPP_GLOBAL_Control
0x180014229  mov     rcx, cs:WPP_GLOBAL_Control
0x180014230  cmp     rcx, rax
0x180014233  jz      short loc_180014291
0x180014235  test    byte ptr [rcx+1Ch], 1
0x180014239  jz      short loc_180014291
0x18001423b  cmp     byte ptr [rcx+19h], 2
0x18001423f  jb      short loc_180014291
0x180014241  mov     edx, 34h ; '4'
0x180014246  mov     r9d, 80041001h
0x18001424c  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180014253  mov     rcx, [rcx+10h]
0x180014257  call    WPP_SF_d
0x18001425c  jmp     short loc_180014291
0x18001425e  dec     eax
0x180014260  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x180014265  jz      short loc_18001427B
0x180014267  lea     r8, asc_1800231B8; "\\"
0x18001426e  mov     edx, 105h; unsigned __int64
0x180014273  mov     rcx, rdi; unsigned __int16 *
0x180014276  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001427b  lea     r8, aRepdrvfsRec; "repdrvfs.rec"
0x180014282  mov     edx, 105h; unsigned __int64
0x180014287  mov     rcx, rdi; unsigned __int16 *
0x18001428a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001428f  mov     edi, esi
0x180014291  mov     rcx, rbx; hKey
0x180014294  call    cs:__imp_RegCloseKey
0x18001429a  mov     eax, edi
0x18001429c  mov     rcx, [rbp+190h+var_30]
0x1800142a3  xor     rcx, rsp; StackCookie
0x1800142a6  call    __security_check_cookie
0x1800142ab  add     rsp, 278h
0x1800142b2  pop     rdi
0x1800142b3  pop     rsi
0x1800142b4  pop     rbx
0x1800142b5  pop     rbp
0x1800142b6  retn
```
