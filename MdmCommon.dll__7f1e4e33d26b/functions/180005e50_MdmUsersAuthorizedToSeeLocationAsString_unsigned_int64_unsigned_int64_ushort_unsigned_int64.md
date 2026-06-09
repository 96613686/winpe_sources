# MdmUsersAuthorizedToSeeLocationAsString(unsigned __int64,unsigned __int64 *,ushort *,unsigned __int64 *)

- ea: `0x180005e50`
- end: `0x180006115`
- name: `?MdmUsersAuthorizedToSeeLocationAsString@@YAJ_KPEA_KPEAG1@Z`
- size: `709`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64 *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180002a24`
- `0x180002de4`
- `0x180002e50`
- `0x180005cb0`
- `0x180005e50`
- `0x1800062a4`
- `0x180006548`
- `0x18001d51c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006044`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006044`

## string_xrefs

- `0x1800060cc`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
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
    v7 = MdmUsersAuthorizedToSeeLocation((__int64 *)&v27, (__int64)a2, (__int64)a3);
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
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v27);
  std::wstring::~wstring((char **)&Src);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005e50  mov     [rsp-8+arg_0], rbx
0x180005e55  push    rbp
0x180005e56  push    rsi
0x180005e57  push    rdi
0x180005e58  push    r12
0x180005e5a  push    r13
0x180005e5c  push    r14
0x180005e5e  push    r15
0x180005e60  lea     rbp, [rsp-27h]
0x180005e65  sub     rsp, 90h
0x180005e6c  mov     rax, cs:__security_cookie
0x180005e73  xor     rax, rsp
0x180005e76  mov     [rbp+57h+var_38], rax
0x180005e7a  mov     r13, r9
0x180005e7d  mov     rdi, r8
0x180005e80  mov     [rbp+57h+var_80], r8
0x180005e84  mov     r12, rdx
0x180005e87  mov     [rbp+57h+var_88], rcx
0x180005e8b  xorps   xmm0, xmm0
0x180005e8e  movups  [rbp+57h+Src], xmm0
0x180005e92  xor     ebx, ebx
0x180005e94  mov     [rbp+57h+var_48], rbx
0x180005e98  mov     [rbp+57h+var_40], 7
0x180005ea0  mov     word ptr [rbp+57h+Src], bx
0x180005ea4  movdqu  [rbp+57h+var_70], xmm0
0x180005ea9  mov     [rbp+57h+var_60], rbx
0x180005ead  cmp     rcx, 1
0x180005eb1  jb      loc_1800060A6
0x180005eb7  test    rdx, rdx
0x180005eba  jnz     short loc_180005EEB
0x180005ebc  mov     r8d, 80070057h
0x180005ec2  mov     esi, r8d
0x180005ec5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005ecc  jz      loc_1800060D9
0x180005ed2  lea     rax, aCprPcactualcou; "CPR(pcActualCount)"
0x180005ed9  mov     [rsp+0C0h+var_98], rax
0x180005ede  mov     dword ptr [rsp+0C0h+var_A0], 34Fh
0x180005ee6  jmp     loc_1800060CC
0x180005eeb  test    r13, r13
0x180005eee  jnz     short loc_180005F1F
0x180005ef0  mov     r8d, 80070057h
0x180005ef6  mov     esi, r8d
0x180005ef9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005f00  jz      loc_1800060D9
0x180005f06  lea     rax, aCprPcchcids; "CPR(pcchCids)"
0x180005f0d  mov     [rsp+0C0h+var_98], rax
0x180005f12  mov     dword ptr [rsp+0C0h+var_A0], 350h
0x180005f1a  jmp     loc_1800060CC
0x180005f1f  mov     [rdx], rbx
0x180005f22  mov     rax, [r9]
0x180005f25  mov     [rbp+57h+var_78], rax
0x180005f29  lea     rcx, [rbp+57h+var_70]
0x180005f2d  call    ?MdmUsersAuthorizedToSeeLocation@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmUsersAuthorizedToSeeLocation(std::vector<std::wstring> *)
0x180005f32  mov     esi, eax
0x180005f34  test    eax, eax
0x180005f36  jns     short loc_180005F61
0x180005f38  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005f3f  jz      loc_1800060D9
0x180005f45  lea     rax, aChrMdmusersaut; "CHR(MdmUsersAuthorizedToSeeLocation(&vC"...
0x180005f4c  mov     [rsp+0C0h+var_98], rax
0x180005f51  mov     dword ptr [rsp+0C0h+var_A0], 357h
0x180005f59  mov     r8d, esi
0x180005f5c  jmp     loc_1800060CC
0x180005f61  mov     r15, rbx
0x180005f64  mov     r14, qword ptr [rbp+57h+var_70]
0x180005f68  mov     rbx, qword ptr [rbp+57h+var_70+8]
0x180005f6c  mov     [rbp+57h+var_90], rbx
0x180005f70  cmp     r14, rbx
0x180005f73  jz      loc_18000600F
0x180005f79  mov     rcx, [rbp+57h+var_48]
0x180005f7d  test    rcx, rcx
0x180005f80  jz      short loc_180005F96
0x180005f82  lea     rdx, asc_180021D50; ","
0x180005f89  lea     rcx, [rbp+57h+Src]; Src
0x180005f8d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180005f92  mov     rcx, [rbp+57h+var_48]
0x180005f96  mov     rdx, [r14+10h]
0x180005f9a  cmp     qword ptr [r14+18h], 7
0x180005f9f  jbe     short loc_180005FA6
0x180005fa1  mov     r9, [r14]
0x180005fa4  jmp     short loc_180005FA9
0x180005fa6  mov     r9, r14
0x180005fa9  mov     rax, [rbp+57h+var_40]
0x180005fad  sub     rax, rcx
0x180005fb0  cmp     rdx, rax
0x180005fb3  ja      short loc_180005FE7
0x180005fb5  lea     rdi, [rdx+rcx]
0x180005fb9  mov     [rbp+57h+var_48], rdi
0x180005fbd  lea     rbx, [rbp+57h+Src]
0x180005fc1  cmp     [rbp+57h+var_40], 7
0x180005fc6  cmova   rbx, qword ptr [rbp+57h+Src]
0x180005fcb  lea     r8, [rdx+rdx]; Size
0x180005fcf  lea     rcx, [rbx+rcx*2]; void *
0x180005fd3  mov     rdx, r9; Src
0x180005fd6  call    memmove_0
0x180005fdb  xor     eax, eax
0x180005fdd  mov     [rbx+rdi*2], ax
0x180005fe1  mov     rbx, [rbp+57h+var_90]
0x180005fe5  jmp     short loc_180005FF5
0x180005fe7  mov     [rsp+0C0h+var_A0], rdx; __int64
0x180005fec  lea     rcx, [rbp+57h+Src]; Src
0x180005ff0  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180005ff5  inc     r15
0x180005ff8  cmp     r15, [rbp+57h+var_88]
0x180005ffc  jnb     short loc_18000600B
0x180005ffe  add     r14, 20h ; ' '
0x180006002  cmp     r14, rbx
0x180006005  jnz     loc_180005F79
0x18000600b  mov     rdi, [rbp+57h+var_80]
0x18000600f  mov     rbx, [rbp+57h+var_48]
0x180006013  inc     rbx
0x180006016  mov     [r12], r15
0x18000601a  mov     [r13+0], rbx
0x18000601e  mov     rax, [rbp+57h+var_78]
0x180006022  cmp     rax, rbx
0x180006025  jb      short loc_18000607F
0x180006027  test    rdi, rdi
0x18000602a  jz      loc_1800060D9
0x180006030  lea     r8, [rbp+57h+Src]
0x180006034  cmp     [rbp+57h+var_40], 7
0x180006039  cmova   r8, qword ptr [rbp+57h+Src]
0x18000603e  mov     rdx, rax
0x180006041  mov     rcx, rdi
0x180006044  call    cs:__imp__o_wcscpy_s
0x18000604a  test    eax, eax
0x18000604c  jnz     short loc_180006058
0x18000604e  mov     [rdi+rbx*2-2], ax
0x180006053  jmp     loc_1800060D9
0x180006058  mov     esi, 80004005h
0x18000605d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006064  jz      short loc_1800060D9
0x180006066  lea     rax, aCbrWcscpySPwsz; "CBR(wcscpy_s(pwszCids, cchCids, wstrCid"...
0x18000606d  mov     [rsp+0C0h+var_98], rax
0x180006072  mov     dword ptr [rsp+0C0h+var_A0], 376h
0x18000607a  jmp     loc_180005F59
0x18000607f  mov     esi, 8007007Ah
0x180006084  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000608b  jz      short loc_1800060D9
0x18000608d  lea     rax, aCbrCchcidsCchn; "CBR(cchCids >= cchNeeded)"
0x180006094  mov     [rsp+0C0h+var_98], rax
0x180006099  mov     dword ptr [rsp+0C0h+var_A0], 371h
0x1800060a1  jmp     loc_180005F59
0x1800060a6  mov     r8d, 80070057h
0x1800060ac  mov     esi, r8d
0x1800060af  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800060b6  jz      short loc_1800060D9
0x1800060b8  lea     rax, aCbrCmaxcount1; "CBR(cMaxCount >= 1)"
0x1800060bf  mov     [rsp+0C0h+var_98], rax
0x1800060c4  mov     dword ptr [rsp+0C0h+var_A0], 34Eh
0x1800060cc  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800060d3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800060d8  nop
0x1800060d9  lea     rcx, [rbp+57h+var_70]
0x1800060dd  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800060e2  nop
0x1800060e3  lea     rcx, [rbp+57h+Src]
0x1800060e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800060ec  mov     eax, esi
0x1800060ee  mov     rcx, [rbp+57h+var_38]
0x1800060f2  xor     rcx, rsp; StackCookie
0x1800060f5  call    __security_check_cookie
0x1800060fa  mov     rbx, [rsp+0C0h+arg_0]
0x180006102  add     rsp, 90h
0x180006109  pop     r15
0x18000610b  pop     r14
0x18000610d  pop     r13
0x18000610f  pop     r12
0x180006111  pop     rdi
0x180006112  pop     rsi
0x180006113  pop     rbp
0x180006114  retn
```
