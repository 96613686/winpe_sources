# MdmUsersAuthorizedToSeeLocationAsString(unsigned __int64,unsigned __int64 *,ushort *,unsigned __int64 *)

- ea: `0x180005ea0`
- end: `0x18000616c`
- name: `?MdmUsersAuthorizedToSeeLocationAsString@@YAJ_KPEA_KPEAG1@Z`
- size: `716`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64 *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180002a24`
- `0x180002de8`
- `0x180002e54`
- `0x180005d00`
- `0x180005ea0`
- `0x18000630c`
- `0x1800065c0`
- `0x18001dbfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006094`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006094`

## string_xrefs

- `0x180006122`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmUsersAuthorizedToSeeLocationAsString(
        unsigned __int64 a1,
        unsigned __int64 *a2,
        unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  unsigned __int16 *v5; // rdi
  int v7; // esi
  int v8; // r8d
  unsigned __int64 v9; // r15
  __int64 *v10; // rbx
  __int64 *v11; // r14
  unsigned __int128 v12; // kr00_16
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  const void *v15; // r9
  __int64 v16; // rdi
  __int128 *p_Src; // rbx
  unsigned __int64 v18; // rbx
  __int128 *v19; // r8
  char v21; // [rsp+20h] [rbp-49h]
  const char *v22; // [rsp+28h] [rbp-41h]
  __int64 *v23; // [rsp+30h] [rbp-39h]
  unsigned __int64 v26; // [rsp+48h] [rbp-21h]
  unsigned __int128 v27; // [rsp+50h] [rbp-19h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h]
  __int128 Src; // [rsp+68h] [rbp-1h] BYREF
  __int64 v30; // [rsp+78h] [rbp+Fh]
  unsigned __int64 v31; // [rsp+80h] [rbp+17h]

  v5 = a3;
  Src = 0;
  v30 = 0;
  v31 = 7;
  LOWORD(Src) = 0;
  v27 = 0;
  v28 = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CBR(cMaxCount >= 1)";
    v21 = 78;
    goto LABEL_38;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        79,
        "CPR(pcActualCount)");
    goto LABEL_39;
  }
  if ( a4 )
  {
    *a2 = 0;
    v26 = *a4;
    v7 = MdmUsersAuthorizedToSeeLocation(&v27);
    if ( v7 >= 0 )
    {
      v9 = 0;
      v10 = (__int64 *)*((_QWORD *)&v27 + 1);
      v12 = v27;
      v23 = (__int64 *)(v12 >> 64);
      v11 = (__int64 *)v12;
      if ( (_QWORD)v27 != *((_QWORD *)&v27 + 1) )
      {
        do
        {
          v13 = v30;
          if ( v30 )
          {
            std::wstring::append(&Src, L",");
            v13 = v30;
          }
          v14 = v11[2];
          if ( (unsigned __int64)v11[3] <= 7 )
            v15 = v11;
          else
            v15 = (const void *)*v11;
          if ( v14 > v31 - v13 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
              &Src,
              v11[2]);
          }
          else
          {
            v16 = v14 + v13;
            v30 = v14 + v13;
            p_Src = &Src;
            if ( v31 > 7 )
              p_Src = (__int128 *)Src;
            memmove_0((char *)p_Src + 2 * v13, v15, 2 * v14);
            *((_WORD *)p_Src + v16) = 0;
            v10 = v23;
          }
          if ( ++v9 >= a1 )
            break;
          v11 += 4;
        }
        while ( v11 != v10 );
        v5 = a3;
      }
      v18 = v30 + 1;
      *a2 = v9;
      *a4 = v18;
      if ( v26 < v18 )
      {
        v7 = -2147024774;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_39;
        v22 = "CBR(cchCids >= cchNeeded)";
        v21 = 113;
      }
      else
      {
        if ( !v5 )
          goto LABEL_39;
        v19 = &Src;
        if ( v31 > 7 )
          v19 = (__int128 *)Src;
        if ( !(unsigned int)_o_wcscpy_s(v5, v26, v19) )
        {
          v5[v18 - 1] = 0;
          goto LABEL_39;
        }
        v7 = -2147467259;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_39;
        v22 = "CBR(wcscpy_s(pwszCids, cchCids, wstrCids.c_str()) == 0)";
        v21 = 118;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_39;
      v22 = "CHR(MdmUsersAuthorizedToSeeLocation(&vCids))";
      v21 = 87;
    }
    v8 = v7;
LABEL_38:
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      (_DWORD)a2,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      v21,
      v22);
    goto LABEL_39;
  }
  v7 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      80,
      "CPR(pcchCids)");
LABEL_39:
  std::vector<std::wstring>::~vector<std::wstring>(&v27);
  std::wstring::~wstring(&Src);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005ea0  mov     [rsp-8+arg_0], rbx
0x180005ea5  push    rbp
0x180005ea6  push    rsi
0x180005ea7  push    rdi
0x180005ea8  push    r12
0x180005eaa  push    r13
0x180005eac  push    r14
0x180005eae  push    r15
0x180005eb0  lea     rbp, [rsp-27h]
0x180005eb5  sub     rsp, 90h
0x180005ebc  mov     rax, cs:__security_cookie
0x180005ec3  xor     rax, rsp
0x180005ec6  mov     [rbp+57h+var_38], rax
0x180005eca  mov     r13, r9
0x180005ecd  mov     rdi, r8
0x180005ed0  mov     [rbp+57h+var_80], r8
0x180005ed4  mov     r12, rdx
0x180005ed7  mov     [rbp+57h+var_88], rcx
0x180005edb  xorps   xmm0, xmm0
0x180005ede  movups  [rbp+57h+Src], xmm0
0x180005ee2  xor     ebx, ebx
0x180005ee4  mov     [rbp+57h+var_48], rbx
0x180005ee8  mov     [rbp+57h+var_40], 7
0x180005ef0  mov     word ptr [rbp+57h+Src], bx
0x180005ef4  movdqu  [rbp+57h+var_70], xmm0
0x180005ef9  mov     [rbp+57h+var_60], rbx
0x180005efd  cmp     rcx, 1
0x180005f01  jb      loc_1800060FC
0x180005f07  test    rdx, rdx
0x180005f0a  jnz     short loc_180005F3B
0x180005f0c  mov     r8d, 80070057h
0x180005f12  mov     esi, r8d
0x180005f15  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005f1c  jz      loc_18000612F
0x180005f22  lea     rax, aCprPcactualcou; "CPR(pcActualCount)"
0x180005f29  mov     [rsp+0C0h+var_98], rax
0x180005f2e  mov     dword ptr [rsp+0C0h+var_A0], 34Fh
0x180005f36  jmp     loc_180006122
0x180005f3b  test    r13, r13
0x180005f3e  jnz     short loc_180005F6F
0x180005f40  mov     r8d, 80070057h
0x180005f46  mov     esi, r8d
0x180005f49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005f50  jz      loc_18000612F
0x180005f56  lea     rax, aCprPcchcids; "CPR(pcchCids)"
0x180005f5d  mov     [rsp+0C0h+var_98], rax
0x180005f62  mov     dword ptr [rsp+0C0h+var_A0], 350h
0x180005f6a  jmp     loc_180006122
0x180005f6f  mov     [rdx], rbx
0x180005f72  mov     rax, [r9]
0x180005f75  mov     [rbp+57h+var_78], rax
0x180005f79  lea     rcx, [rbp+57h+var_70]
0x180005f7d  call    ?MdmUsersAuthorizedToSeeLocation@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmUsersAuthorizedToSeeLocation(std::vector<std::wstring> *)
0x180005f82  mov     esi, eax
0x180005f84  test    eax, eax
0x180005f86  jns     short loc_180005FB1
0x180005f88  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005f8f  jz      loc_18000612F
0x180005f95  lea     rax, aChrMdmusersaut; "CHR(MdmUsersAuthorizedToSeeLocation(&vC"...
0x180005f9c  mov     [rsp+0C0h+var_98], rax
0x180005fa1  mov     dword ptr [rsp+0C0h+var_A0], 357h
0x180005fa9  mov     r8d, esi
0x180005fac  jmp     loc_180006122
0x180005fb1  mov     r15, rbx
0x180005fb4  mov     r14, qword ptr [rbp+57h+var_70]
0x180005fb8  mov     rbx, qword ptr [rbp+57h+var_70+8]
0x180005fbc  mov     [rbp+57h+var_90], rbx
0x180005fc0  cmp     r14, rbx
0x180005fc3  jz      loc_18000605F
0x180005fc9  mov     rcx, [rbp+57h+var_48]
0x180005fcd  test    rcx, rcx
0x180005fd0  jz      short loc_180005FE6
0x180005fd2  lea     rdx, asc_180021D50; ","
0x180005fd9  lea     rcx, [rbp+57h+Src]; Src
0x180005fdd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180005fe2  mov     rcx, [rbp+57h+var_48]
0x180005fe6  mov     rdx, [r14+10h]
0x180005fea  cmp     qword ptr [r14+18h], 7
0x180005fef  jbe     short loc_180005FF6
0x180005ff1  mov     r9, [r14]
0x180005ff4  jmp     short loc_180005FF9
0x180005ff6  mov     r9, r14
0x180005ff9  mov     rax, [rbp+57h+var_40]
0x180005ffd  sub     rax, rcx
0x180006000  cmp     rdx, rax
0x180006003  ja      short loc_180006037
0x180006005  lea     rdi, [rdx+rcx]
0x180006009  mov     [rbp+57h+var_48], rdi
0x18000600d  lea     rbx, [rbp+57h+Src]
0x180006011  cmp     [rbp+57h+var_40], 7
0x180006016  cmova   rbx, qword ptr [rbp+57h+Src]
0x18000601b  lea     r8, [rdx+rdx]; Size
0x18000601f  lea     rcx, [rbx+rcx*2]; void *
0x180006023  mov     rdx, r9; Src
0x180006026  call    memmove_0
0x18000602b  xor     eax, eax
0x18000602d  mov     [rbx+rdi*2], ax
0x180006031  mov     rbx, [rbp+57h+var_90]
0x180006035  jmp     short loc_180006045
0x180006037  mov     [rsp+0C0h+var_A0], rdx; __int64
0x18000603c  lea     rcx, [rbp+57h+Src]; Src
0x180006040  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180006045  inc     r15
0x180006048  cmp     r15, [rbp+57h+var_88]
0x18000604c  jnb     short loc_18000605B
0x18000604e  add     r14, 20h ; ' '
0x180006052  cmp     r14, rbx
0x180006055  jnz     loc_180005FC9
0x18000605b  mov     rdi, [rbp+57h+var_80]
0x18000605f  mov     rbx, [rbp+57h+var_48]
0x180006063  inc     rbx
0x180006066  mov     [r12], r15
0x18000606a  mov     [r13+0], rbx
0x18000606e  mov     rax, [rbp+57h+var_78]
0x180006072  cmp     rax, rbx
0x180006075  jb      short loc_1800060D5
0x180006077  test    rdi, rdi
0x18000607a  jz      loc_18000612F
0x180006080  lea     r8, [rbp+57h+Src]
0x180006084  cmp     [rbp+57h+var_40], 7
0x180006089  cmova   r8, qword ptr [rbp+57h+Src]
0x18000608e  mov     rdx, rax
0x180006091  mov     rcx, rdi
0x180006094  call    cs:__imp__o_wcscpy_s
0x18000609b  nop     dword ptr [rax+rax+00h]
0x1800060a0  test    eax, eax
0x1800060a2  jnz     short loc_1800060AE
0x1800060a4  mov     [rdi+rbx*2-2], ax
0x1800060a9  jmp     loc_18000612F
0x1800060ae  mov     esi, 80004005h
0x1800060b3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800060ba  jz      short loc_18000612F
0x1800060bc  lea     rax, aCbrWcscpySPwsz; "CBR(wcscpy_s(pwszCids, cchCids, wstrCid"...
0x1800060c3  mov     [rsp+0C0h+var_98], rax
0x1800060c8  mov     dword ptr [rsp+0C0h+var_A0], 376h
0x1800060d0  jmp     loc_180005FA9
0x1800060d5  mov     esi, 8007007Ah
0x1800060da  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800060e1  jz      short loc_18000612F
0x1800060e3  lea     rax, aCbrCchcidsCchn; "CBR(cchCids >= cchNeeded)"
0x1800060ea  mov     [rsp+0C0h+var_98], rax
0x1800060ef  mov     dword ptr [rsp+0C0h+var_A0], 371h
0x1800060f7  jmp     loc_180005FA9
0x1800060fc  mov     r8d, 80070057h
0x180006102  mov     esi, r8d
0x180006105  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000610c  jz      short loc_18000612F
0x18000610e  lea     rax, aCbrCmaxcount1; "CBR(cMaxCount >= 1)"
0x180006115  mov     [rsp+0C0h+var_98], rax
0x18000611a  mov     dword ptr [rsp+0C0h+var_A0], 34Eh
0x180006122  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180006129  call    McTemplateU0dsqs_EventWriteTransfer
0x18000612e  nop
0x18000612f  lea     rcx, [rbp+57h+var_70]
0x180006133  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180006138  nop
0x180006139  lea     rcx, [rbp+57h+Src]
0x18000613d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006142  mov     eax, esi
0x180006144  mov     rcx, [rbp+57h+var_38]
0x180006148  xor     rcx, rsp; StackCookie
0x18000614b  call    __security_check_cookie
0x180006150  mov     rbx, [rsp+0C0h+arg_0]
0x180006158  add     rsp, 90h
0x18000615f  pop     r15
0x180006161  pop     r14
0x180006163  pop     r13
0x180006165  pop     r12
0x180006167  pop     rdi
0x180006168  pop     rsi
0x180006169  pop     rbp
0x18000616a  retn
```
