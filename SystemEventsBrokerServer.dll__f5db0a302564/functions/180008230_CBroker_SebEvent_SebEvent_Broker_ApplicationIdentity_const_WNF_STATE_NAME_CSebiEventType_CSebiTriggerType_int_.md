# CBroker::SebEvent::SebEvent(Broker::ApplicationIdentity const &,_WNF_STATE_NAME,_CSebiEventType,_CSebiTriggerType,int,_CSebConditionOperator,ulong,CBroker::_CustomData const *,ulong,int,int,ulong,ulong,ulong,ulong,CBroker::SebBroker *)

- ea: `0x180008230`
- end: `0x1800085ae`
- name: `??0SebEvent@CBroker@@QEAA@AEBUApplicationIdentity@Broker@@U_WNF_STATE_NAME@@W4_CSebiEventType@@W4_CSebiTriggerType@@HW4_CSebConditionOperator@@KPEBU_CustomData@1@KHHKKKKPEAVSebBroker@1@@Z`
- size: `894`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, int, ULONG SecurityDescriptorSize, int, int, int, __int64, int, int, int, int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007700`

## callees

- `0x1800030e0`
- `0x180008230`
- `0x1800085c0`
- `0x18001732c`
- `0x1800195e0`
- `0x18001a540`
- `0x18001cf74`
- `0x18001d39c`
- `0x18001d9ac`
- `0x180022440`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180008458`
- `ntdll!NtCreateWnfStateName` at `0x180008458`
- `ntdll!RtlInitializeSRWLock` at `0x1800083d3`
- `ntdll!RtlInitializeSRWLock` at `0x1800083d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800083be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800083be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008479`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008479`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBroker::SebEvent::SebEvent(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        int a4,
        ULONG SecurityDescriptorSize,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        int a16,
        __int64 a17)
{
  __int64 v21; // rsi
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  int v24; // ebx
  int v25; // eax
  __int64 v26; // rbx
  _DWORD *v28; // r14
  unsigned int v29; // eax
  void *v30; // rax
  void **v31; // [rsp+40h] [rbp-49h] BYREF
  __int128 v32; // [rsp+48h] [rbp-41h]
  int v33; // [rsp+58h] [rbp-31h]
  unsigned int v34; // [rsp+60h] [rbp-29h]
  _QWORD pExceptionObject[3]; // [rsp+68h] [rbp-21h] BYREF
  int v36; // [rsp+80h] [rbp-9h]
  unsigned int v37; // [rsp+88h] [rbp-1h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+D8h] [rbp+4Fh] BYREF
  __int64 v39; // [rsp+E0h] [rbp+57h]

  *(_QWORD *)a1 = &CBroker::SebEvent::`vftable';
  v21 = a1 + 8;
  v39 = a1 + 8;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(a1 + 8, a2[1] - *a2, a2);
  v22 = a2 + 3;
  *(_OWORD *)(v21 + 24) = 0;
  *(_QWORD *)(v21 + 40) = 0;
  *(_QWORD *)(v21 + 48) = 0;
  if ( a2[6] > 7u )
    v22 = (_QWORD *)*v22;
  std::wstring::_Construct<2,unsigned short const *>(v21 + 24, v22, a2[5]);
  v23 = a2 + 7;
  *(_OWORD *)(v21 + 56) = 0;
  *(_QWORD *)(v21 + 72) = 0;
  *(_QWORD *)(v21 + 80) = 0;
  if ( a2[10] > 7u )
    v23 = (_QWORD *)*v23;
  std::wstring::_Construct<2,unsigned short const *>(v21 + 56, v23, a2[9]);
  *(_DWORD *)(a1 + 96) = a4;
  *(_DWORD *)(a1 + 100) = SecurityDescriptorSize;
  *(_QWORD *)(a1 + 104) = a3;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 152) = 0;
  *(_DWORD *)(a1 + 156) = a6;
  *(_BYTE *)(a1 + 161) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_DWORD *)(a1 + 176) = 8;
  *(_QWORD *)(a1 + 184) = a17;
  v24 = a7;
  *(_DWORD *)(a1 + 208) = a7;
  *(_DWORD *)(a1 + 212) = a10;
  *(_DWORD *)(a1 + 216) = a11;
  *(_DWORD *)(a1 + 220) = a12;
  *(_DWORD *)(a1 + 224) = a13;
  *(_DWORD *)(a1 + 228) = a14;
  *(_DWORD *)(a1 + 232) = a15;
  *(_DWORD *)(a1 + 236) = a16;
  *(_DWORD *)(a1 + 248) = a8;
  *(_DWORD *)(a1 + 252) = 0;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;WD)(A;;GA;;;SY)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&v31);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v34);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v31);
    v36 = v33;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v37 = v34;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  RtlInitializeSRWLock(a1 + 240);
  *(_BYTE *)(a1 + 160) = 0;
  v25 = *(_DWORD *)(a1 + 100);
  if ( v24 == 2 )
  {
    if ( (unsigned int)(v25 - 2) <= 1 )
      *(_DWORD *)(a1 + 248) = 1;
    *(_DWORD *)(a1 + 208) = 2;
  }
  else
  {
    if ( (unsigned int)(v25 - 2) <= 1 )
    {
      *(_DWORD *)(a1 + 248) = 1;
LABEL_9:
      *(_DWORD *)(a1 + 208) = 1;
      goto LABEL_10;
    }
    if ( v25 == 1 )
      goto LABEL_9;
  }
LABEL_10:
  *(_QWORD *)(a1 + 256) = 0;
  v26 = a9;
  if ( a9 )
  {
    v28 = operator new(0x10u);
    v28[3] = *(_DWORD *)(v26 + 12);
    v29 = *(_DWORD *)(v26 + 8);
    v28[2] = v29;
    if ( v29 )
    {
      v30 = operator new[](v29);
      *(_QWORD *)v28 = v30;
      memcpy_0(v30, *(const void **)v26, (unsigned int)v28[2]);
    }
    else
    {
      *(_QWORD *)v28 = 0;
    }
    *(_QWORD *)(a1 + 256) = v28;
  }
  if ( (int)NtCreateWnfStateName(a1 + 112, 3, 0) < 0 )
  {
    v32 = 0;
    v33 = 7;
    v31 = &Broker::EventInternalError::`vftable';
    throw (Broker::EventInternalError *)&v31;
  }
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 120) = *(_QWORD *)(a1 + 112);
  LocalFree(SecurityDescriptor);
  return a1;
}

```

## disassembly

```asm
0x180008230  mov     [rsp-8+arg_0], rcx
0x180008235  push    rbp
0x180008236  push    rbx
0x180008237  push    rsi
0x180008238  push    rdi
0x180008239  push    r12
0x18000823b  push    r14
0x18000823d  push    r15
0x18000823f  lea     rbp, [rsp-7]
0x180008244  sub     rsp, 90h
0x18000824b  mov     r15d, r9d
0x18000824e  mov     rbx, r8
0x180008251  mov     r14, rdx
0x180008254  mov     rdi, rcx
0x180008257  lea     rax, ??_7SebEvent@CBroker@@6B@; const CBroker::SebEvent::`vftable'
0x18000825e  mov     [rcx], rax
0x180008261  lea     rsi, [rcx+8]
0x180008265  mov     [rbp+37h+arg_10], rsi
0x180008269  xor     r12d, r12d
0x18000826c  mov     [rsi], r12
0x18000826f  mov     [rsi+8], r12
0x180008273  mov     [rsi+10h], r12
0x180008277  lea     r9, [rdx+8]
0x18000827b  mov     rdx, [r9]
0x18000827e  sub     rdx, [r14]
0x180008281  mov     r8, r14
0x180008284  mov     rcx, rsi
0x180008287  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x18000828c  nop
0x18000828d  lea     rcx, [rsi+18h]
0x180008291  lea     rdx, [r14+18h]
0x180008295  xorps   xmm0, xmm0
0x180008298  movups  xmmword ptr [rcx], xmm0
0x18000829b  mov     [rcx+10h], r12
0x18000829f  mov     [rcx+18h], r12
0x1800082a3  mov     r8, [rdx+10h]
0x1800082a7  cmp     qword ptr [rdx+18h], 7
0x1800082ac  jbe     short loc_1800082B1
0x1800082ae  mov     rdx, [rdx]
0x1800082b1  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800082b6  nop
0x1800082b7  lea     rcx, [rsi+38h]
0x1800082bb  lea     rdx, [r14+38h]
0x1800082bf  xorps   xmm0, xmm0
0x1800082c2  movups  xmmword ptr [rcx], xmm0
0x1800082c5  mov     [rcx+10h], r12
0x1800082c9  mov     [rcx+18h], r12
0x1800082cd  mov     r8, [rdx+10h]
0x1800082d1  cmp     qword ptr [rdx+18h], 7
0x1800082d6  ja      loc_1800084A3
0x1800082dc  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800082e1  nop
0x1800082e2  mov     [rdi+60h], r15d
0x1800082e6  mov     eax, [rbp+37h+SecurityDescriptorSize]
0x1800082e9  mov     [rdi+64h], eax
0x1800082ec  mov     [rdi+68h], rbx
0x1800082f0  mov     [rdi+88h], r12
0x1800082f7  mov     [rdi+90h], r12
0x1800082fe  mov     [rdi+98h], r12d
0x180008305  mov     eax, [rbp+37h+arg_28]
0x180008308  mov     [rdi+9Ch], eax
0x18000830e  mov     byte ptr [rdi+0A1h], 0
0x180008315  mov     [rdi+0A8h], r12
0x18000831c  mov     esi, 8
0x180008321  mov     [rdi+0B0h], esi
0x180008327  mov     rax, [rbp+37h+arg_80]
0x18000832e  mov     [rdi+0B8h], rax
0x180008335  mov     ebx, [rbp+37h+arg_30]
0x180008338  mov     [rdi+0D0h], ebx
0x18000833e  mov     eax, [rbp+37h+arg_48]
0x180008344  mov     [rdi+0D4h], eax
0x18000834a  mov     eax, [rbp+37h+arg_50]
0x180008350  mov     [rdi+0D8h], eax
0x180008356  mov     eax, [rbp+37h+arg_58]
0x18000835c  mov     [rdi+0DCh], eax
0x180008362  mov     eax, [rbp+37h+arg_60]
0x180008368  mov     [rdi+0E0h], eax
0x18000836e  mov     eax, [rbp+37h+arg_68]
0x180008374  mov     [rdi+0E4h], eax
0x18000837a  mov     eax, [rbp+37h+arg_70]
0x180008380  mov     [rdi+0E8h], eax
0x180008386  mov     eax, [rbp+37h+arg_78]
0x18000838c  mov     [rdi+0ECh], eax
0x180008392  mov     eax, [rbp+37h+arg_38]
0x180008395  mov     [rdi+0F8h], eax
0x18000839b  mov     [rdi+0FCh], r12d
0x1800083a2  mov     [rbp+37h+SecurityDescriptorSize], r12d
0x1800083a6  mov     [rbp+37h+SecurityDescriptor], r12
0x1800083aa  lea     r9, [rbp+37h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800083ae  lea     r8, [rbp+37h+SecurityDescriptor]; SecurityDescriptor
0x1800083b2  mov     edx, 1; StringSDRevision
0x1800083b7  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)(A;;GA;;;SY)"
0x1800083be  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800083c4  test    eax, eax
0x1800083c6  jz      loc_1800084CE
0x1800083cc  lea     rcx, [rdi+0F0h]
0x1800083d3  call    cs:__imp_RtlInitializeSRWLock
0x1800083d9  mov     byte ptr [rdi+0A0h], 0
0x1800083e0  mov     eax, [rdi+64h]
0x1800083e3  cmp     ebx, 2
0x1800083e6  jz      loc_1800084AB
0x1800083ec  lea     ecx, [rax-2]
0x1800083ef  cmp     ecx, 1
0x1800083f2  ja      loc_180008495
0x1800083f8  mov     dword ptr [rdi+0F8h], 1
0x180008402  mov     dword ptr [rdi+0D0h], 1
0x18000840c  mov     [rdi+100h], r12
0x180008413  mov     rbx, [rbp+37h+arg_40]
0x18000841a  test    rbx, rbx
0x18000841d  jnz     loc_18000853C
0x180008423  mov     eax, [rdi+64h]
0x180008426  test    eax, 0FFFFFFFCh
0x18000842b  jnz     short loc_180008437
0x18000842d  cmp     eax, 1
0x180008430  jz      short loc_180008437
0x180008432  mov     esi, 1000h
0x180008437  mov     rax, [rbp+37h+SecurityDescriptor]
0x18000843b  mov     [rsp+0C0h+var_90], rax
0x180008440  mov     [rsp+0C0h+var_98], esi
0x180008444  mov     [rsp+0C0h+var_A0], r12
0x180008449  xor     r9d, r9d
0x18000844c  xor     r8d, r8d
0x18000844f  mov     edx, 3
0x180008454  lea     rcx, [rdi+70h]
0x180008458  call    cs:__imp_NtCreateWnfStateName
0x18000845e  test    eax, eax
0x180008460  js      loc_180008584
0x180008466  mov     [rdi+80h], r12
0x18000846d  mov     rax, [rdi+70h]
0x180008471  mov     [rdi+78h], rax
0x180008475  mov     rcx, [rbp+37h+SecurityDescriptor]; hMem
0x180008479  call    cs:__imp_LocalFree
0x18000847f  nop
0x180008480  mov     rax, rdi
0x180008483  add     rsp, 90h
0x18000848a  pop     r15
0x18000848c  pop     r14
0x18000848e  pop     r12
0x180008490  pop     rdi
0x180008491  pop     rsi
0x180008492  pop     rbx
0x180008493  pop     rbp
0x180008494  retn
0x180008495  cmp     eax, 1
0x180008498  jz      loc_180008402
0x18000849e  jmp     loc_18000840C
0x1800084a3  mov     rdx, [rdx]
0x1800084a6  jmp     loc_1800082DC
0x1800084ab  add     eax, 0FFFFFFFEh
0x1800084ae  cmp     eax, 1
0x1800084b1  jbe     short loc_1800084C2
0x1800084b3  mov     dword ptr [rdi+0D0h], 2
0x1800084bd  jmp     loc_18000840C
0x1800084c2  mov     dword ptr [rdi+0F8h], 1
0x1800084cc  jmp     short loc_1800084B3
0x1800084ce  lea     rcx, [rbp+37h+var_80]; this
0x1800084d2  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800084d7  nop
0x1800084d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084df  test    dword ptr [rcx+1Ch], 400h
0x1800084e6  jz      short loc_180008507
0x1800084e8  cmp     byte ptr [rcx+19h], 2
0x1800084ec  jb      short loc_180008507
0x1800084ee  mov     edx, 0Ah
0x1800084f3  mov     r9d, [rbp+37h+var_60]
0x1800084f7  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x1800084fe  mov     rcx, [rcx+10h]
0x180008502  call    WPP_SF_d
0x180008507  lea     rdx, [rbp+37h+var_80]; struct std::exception *
0x18000850b  lea     rcx, [rbp+37h+pExceptionObject]; this
0x18000850f  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180008514  mov     eax, [rbp+37h+var_68]
0x180008517  mov     [rbp+37h+var_40], eax
0x18000851a  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180008521  mov     [rbp+37h+pExceptionObject], rax
0x180008525  mov     eax, [rbp+37h+var_60]
0x180008528  mov     [rbp+37h+var_38], eax
0x18000852b  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180008532  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x180008536  call    _CxxThrowException_0
0x18000853c  mov     ecx, 10h; Size
0x180008541  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008546  mov     r14, rax
0x180008549  mov     ecx, [rbx+0Ch]
0x18000854c  mov     [rax+0Ch], ecx
0x18000854f  mov     eax, [rbx+8]
0x180008552  mov     [r14+8], eax
0x180008556  test    eax, eax
0x180008558  jz      short loc_180008575
0x18000855a  mov     ecx, eax; unsigned __int64
0x18000855c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008561  mov     [r14], rax
0x180008564  mov     r8d, [r14+8]; Size
0x180008568  mov     rdx, [rbx]; Src
0x18000856b  mov     rcx, rax; void *
0x18000856e  call    memcpy_0
0x180008573  jmp     short loc_180008578
0x180008575  mov     [r14], r12
0x180008578  mov     [rdi+100h], r14
0x18000857f  jmp     loc_180008423
0x180008584  xorps   xmm0, xmm0
0x180008587  movups  [rbp+37h+var_78], xmm0
0x18000858b  mov     [rbp+37h+var_68], 7
0x180008592  lea     rax, ??_7EventInternalError@Broker@@6B@; const Broker::EventInternalError::`vftable'
0x180008599  mov     [rbp+37h+var_80], rax
0x18000859d  lea     rdx, _TI3?AUEventInternalError@Broker@@; pThrowInfo
0x1800085a4  lea     rcx, [rbp+37h+var_80]; pExceptionObject
0x1800085a8  call    _CxxThrowException_0
```
