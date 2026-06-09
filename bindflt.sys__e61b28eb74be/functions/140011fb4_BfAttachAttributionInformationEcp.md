# BfAttachAttributionInformationEcp

- ea: `0x140011fb4`
- end: `0x1400123d4`
- name: `BfAttachAttributionInformationEcp`
- size: `1056`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140011eb0`

## callees

- `0x1400034c8`
- `0x140004b90`
- `0x140004cc0`
- `0x140004fc0`
- `0x140011c9c`
- `0x140011d18`
- `0x140011df0`
- `0x140011e30`
- `0x140011fb4`

## import_xrefs

- `ntoskrnl!PsGetThreadTeb` at `0x14001209d`
- `ntoskrnl!PsGetThreadTeb` at `0x14001209d`
- `ntoskrnl!PsGetProcessPeb` at `0x14001208b`
- `ntoskrnl!PsGetProcessPeb` at `0x14001208b`
- `FLTMGR!FltGetRequestorProcess` at `0x14001206b`
- `FLTMGR!FltGetRequestorProcess` at `0x14001206b`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140012354`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140012354`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x1400121ab`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x1400121ab`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001236f`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001239d`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001236f`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001239d`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140012049`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140012049`

## pseudocode

```c
__int64 __fastcall BfAttachAttributionInformationEcp(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        struct _ECP_LIST *a3,
        _BYTE *a4)
{
  NTSTATUS ExtraCreateParameter; // ebx
  __int64 ProcessPeb; // rdi
  __int64 ThreadTeb; // r14
  PEPROCESS RequestorProcess; // rax
  int v11; // ebx
  PETHREAD Thread; // rsi
  size_t v13; // r13
  size_t v14; // rsi
  unsigned int v15; // edx
  unsigned int v16; // edx
  size_t v17; // rcx
  unsigned int v18; // ecx
  PVOID EcpContext; // [rsp+40h] [rbp-238h] BYREF
  ULONG EcpContextSize; // [rsp+48h] [rbp-230h] BYREF
  int v22; // [rsp+4Ch] [rbp-22Ch]
  unsigned int v23; // [rsp+50h] [rbp-228h]
  int v24; // [rsp+54h] [rbp-224h]
  size_t Size; // [rsp+58h] [rbp-220h] BYREF
  size_t v26; // [rsp+60h] [rbp-218h] BYREF
  __int64 v27; // [rsp+68h] [rbp-210h] BYREF
  PECP_LIST EcpList; // [rsp+70h] [rbp-208h]
  __int64 v29; // [rsp+78h] [rbp-200h]
  void *v30[2]; // [rsp+80h] [rbp-1F8h] BYREF
  void *v31[2]; // [rsp+90h] [rbp-1E8h] BYREF
  _BYTE v32[144]; // [rsp+A0h] [rbp-1D8h] BYREF
  _BYTE Src[256]; // [rsp+130h] [rbp-148h] BYREF

  EcpList = a3;
  v29 = a2;
  EcpContext = 0;
  EcpContextSize = 0;
  v27 = 0;
  *(_OWORD *)v30 = 0;
  *(_OWORD *)v31 = 0;
  Size = 256;
  v26 = 132;
  *a4 = 0;
  ExtraCreateParameter = FltFindExtraCreateParameter(
                           *(PFLT_FILTER *)(a2 + 8),
                           a3,
                           &GUID_ECP_CLOUDFILES_ATTRIBUTION,
                           &EcpContext,
                           &EcpContextSize);
  if ( ExtraCreateParameter == -1073741275 )
  {
    ProcessPeb = 0;
    ThreadTeb = 0;
    RequestorProcess = FltGetRequestorProcess(CallbackData);
    v11 = (int)RequestorProcess;
    if ( RequestorProcess )
    {
      Thread = CallbackData->Thread;
      if ( Thread )
      {
        ProcessPeb = PsGetProcessPeb(RequestorProcess);
        ThreadTeb = PsGetThreadTeb(Thread);
      }
    }
    if ( ProcessPeb && ThreadTeb )
    {
      if ( (int)BfQueryPackageIdentity(v11, (unsigned int)Src, (unsigned int)&Size, (unsigned int)v32, (__int64)&v26) < 0 )
      {
        Size = 0;
        v26 = 0;
      }
      v24 = 0;
      v23 = 0;
      EcpContextSize = 80;
      ExtraCreateParameter = BfGetProcessParameters(ProcessPeb, &v27);
      v22 = ExtraCreateParameter;
      if ( ExtraCreateParameter >= 0 )
      {
        BfExtractPebStrings(v27, v30, v31);
        v13 = LOWORD(v30[0]);
        v14 = LOWORD(v31[0]);
        EcpContextSize += v26 + 2 + LOWORD(v31[0]) + LOWORD(v30[0]) + 2 + 2 + Size + 2;
        ExtraCreateParameter = FltAllocateExtraCreateParameter(
                                 *(PFLT_FILTER *)(a2 + 8),
                                 &GUID_ECP_CLOUDFILES_ATTRIBUTION,
                                 EcpContextSize,
                                 0,
                                 0,
                                 0x69614642u,
                                 &EcpContext);
        v22 = ExtraCreateParameter;
        if ( ExtraCreateParameter >= 0 )
        {
          memset(EcpContext, 0, EcpContextSize);
          *(_DWORD *)EcpContext = EcpContextSize;
          BfFillOutEcpFields(EcpContext, ProcessPeb, ThreadTeb);
          *((_WORD *)EcpContext + 29) = 0;
          *((_WORD *)EcpContext + 30) = v13 >> 1;
          v15 = (unsigned __int16)(v13 >> 1) + 1;
          v23 = v15;
          if ( v15 <= 0xFFFF )
          {
            *((_WORD *)EcpContext + 31) = v15;
            *((_WORD *)EcpContext + 32) = v14 >> 1;
            v24 = (unsigned __int16)(v13 >> 1) + 1;
            v16 = (unsigned __int16)(v14 >> 1) + 1 + v15;
            v23 = v16;
            if ( v16 <= 0xFFFF )
            {
              *((_WORD *)EcpContext + 33) = v16;
              v17 = Size >> 1;
              *((_WORD *)EcpContext + 34) = Size >> 1;
              v24 = v16;
              v18 = v16 + (unsigned __int16)v17 + 1;
              v23 = v18;
              if ( v18 <= 0xFFFF )
              {
                *((_WORD *)EcpContext + 35) = v18;
                *((_WORD *)EcpContext + 36) = v26 >> 1;
                RtlCopyFromUser((char *)EcpContext + 2 * *((unsigned __int16 *)EcpContext + 29) + 74, v30[1], v13);
                RtlCopyFromUser((char *)EcpContext + 2 * *((unsigned __int16 *)EcpContext + 31) + 74, v31[1], v14);
                memmove((char *)EcpContext + 2 * *((unsigned __int16 *)EcpContext + 33) + 74, Src, Size);
                memmove((char *)EcpContext + 2 * *((unsigned __int16 *)EcpContext + 35) + 74, v32, v26);
                ExtraCreateParameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)(a2 + 8), EcpList, EcpContext);
                if ( ExtraCreateParameter >= 0 )
                  *a4 = 1;
                else
                  FltFreeExtraCreateParameter(*(PFLT_FILTER *)(a2 + 8), EcpContext);
              }
              else
              {
                ExtraCreateParameter = -1073741811;
                v22 = -1073741811;
              }
            }
            else
            {
              ExtraCreateParameter = -1073741811;
              v22 = -1073741811;
            }
          }
          else
          {
            ExtraCreateParameter = -1073741811;
            v22 = -1073741811;
          }
        }
      }
    }
    else
    {
      return 0;
    }
  }
  return (unsigned int)ExtraCreateParameter;
}

```

## disassembly

```asm
0x140011fb4  push    rbx
0x140011fb6  push    rsi
0x140011fb7  push    rdi
0x140011fb8  push    r12
0x140011fba  push    r13
0x140011fbc  push    r14
0x140011fbe  push    r15
0x140011fc0  sub     rsp, 240h
0x140011fc7  mov     rax, cs:__security_cookie
0x140011fce  xor     rax, rsp
0x140011fd1  mov     [rsp+278h+var_48], rax
0x140011fd9  mov     r12, r9
0x140011fdc  mov     rax, r8
0x140011fdf  mov     [rsp+278h+EcpList], rax
0x140011fe4  mov     r15, rdx
0x140011fe7  mov     rsi, rcx
0x140011fea  mov     [rsp+278h+var_200], rdx
0x140011fef  xor     r13d, r13d
0x140011ff2  mov     [rsp+278h+EcpContext], r13
0x140011ff7  mov     [rsp+278h+var_230], r13d
0x140011ffc  mov     [rsp+278h+var_210], r13
0x140012001  xorps   xmm0, xmm0
0x140012004  movups  xmmword ptr [rsp+278h+var_1F8], xmm0
0x14001200c  xorps   xmm1, xmm1
0x14001200f  movups  xmmword ptr [rsp+278h+var_1E8], xmm1
0x140012017  mov     [rsp+278h+Size], 100h
0x140012020  mov     [rsp+278h+var_218], 84h
0x140012029  mov     [r9], r13b
0x14001202c  lea     rcx, [rsp+278h+var_230]
0x140012031  mov     [rsp+278h+EcpContextSize], rcx; EcpContextSize
0x140012036  lea     r9, [rsp+278h+EcpContext]; EcpContext
0x14001203b  lea     r8, GUID_ECP_CLOUDFILES_ATTRIBUTION; EcpType
0x140012042  mov     rdx, rax; EcpList
0x140012045  mov     rcx, [r15+8]; Filter
0x140012049  call    cs:__imp_FltFindExtraCreateParameter
0x140012050  nop     dword ptr [rax+rax+00h]
0x140012055  mov     ebx, eax
0x140012057  cmp     eax, 0C0000225h
0x14001205c  jnz     loc_1400123AE
0x140012062  mov     edi, r13d
0x140012065  mov     r14d, r13d
0x140012068  mov     rcx, rsi; CallbackData
0x14001206b  call    cs:__imp_FltGetRequestorProcess
0x140012072  nop     dword ptr [rax+rax+00h]
0x140012077  mov     rbx, rax
0x14001207a  test    rax, rax
0x14001207d  jz      short loc_1400120AC
0x14001207f  mov     rsi, [rsi+8]
0x140012083  test    rsi, rsi
0x140012086  jz      short loc_1400120AC
0x140012088  mov     rcx, rax
0x14001208b  call    cs:__imp_PsGetProcessPeb
0x140012092  nop     dword ptr [rax+rax+00h]
0x140012097  mov     rdi, rax
0x14001209a  mov     rcx, rsi
0x14001209d  call    cs:__imp_PsGetThreadTeb
0x1400120a4  nop     dword ptr [rax+rax+00h]
0x1400120a9  mov     r14, rax
0x1400120ac  test    rdi, rdi
0x1400120af  jz      loc_1400123AB
0x1400120b5  test    r14, r14
0x1400120b8  jz      loc_1400123AB
0x1400120be  lea     rax, [rsp+278h+var_218]
0x1400120c3  mov     [rsp+278h+EcpContextSize], rax
0x1400120c8  lea     r9, [rsp+278h+var_1D8]
0x1400120d0  lea     r8, [rsp+278h+Size]
0x1400120d5  lea     rdx, [rsp+278h+Src]
0x1400120dd  mov     rcx, rbx
0x1400120e0  call    BfQueryPackageIdentity
0x1400120e5  test    eax, eax
0x1400120e7  jns     short loc_1400120F3
0x1400120e9  mov     [rsp+278h+Size], r13
0x1400120ee  mov     [rsp+278h+var_218], r13
0x1400120f3  mov     [rsp+278h+var_224], r13d
0x1400120f8  mov     [rsp+278h+var_228], r13d
0x1400120fd  mov     [rsp+278h+var_230], 50h ; 'P'
0x140012105  lea     rdx, [rsp+278h+var_210]
0x14001210a  mov     rcx, rdi
0x14001210d  call    BfGetProcessParameters
0x140012112  mov     ebx, eax
0x140012114  mov     [rsp+278h+var_22C], eax
0x140012118  test    eax, eax
0x14001211a  js      loc_1400123AE
0x140012120  lea     r8, [rsp+278h+var_1E8]
0x140012128  lea     rdx, [rsp+278h+var_1F8]
0x140012130  mov     rcx, [rsp+278h+var_210]
0x140012135  call    BfExtractPebStrings
0x14001213a  movzx   r13d, word ptr [rsp+278h+var_1F8]
0x140012143  mov     ecx, [rsp+278h+var_230]
0x140012147  add     ecx, 2
0x14001214a  add     ecx, r13d
0x14001214d  mov     [rsp+278h+var_230], ecx
0x140012151  movzx   esi, word ptr [rsp+278h+var_1E8]
0x140012159  add     ecx, 2
0x14001215c  add     ecx, esi
0x14001215e  mov     [rsp+278h+var_230], ecx
0x140012162  mov     r8d, dword ptr [rsp+278h+Size]
0x140012167  add     r8d, 2
0x14001216b  add     r8d, ecx
0x14001216e  mov     [rsp+278h+var_230], r8d
0x140012173  mov     eax, dword ptr [rsp+278h+var_218]
0x140012177  add     eax, 2
0x14001217a  add     r8d, eax; SizeOfContext
0x14001217d  mov     [rsp+278h+var_230], r8d
0x140012182  lea     rax, [rsp+278h+EcpContext]
0x140012187  mov     [rsp+278h+var_248], rax; EcpContext
0x14001218c  mov     [rsp+278h+PoolTag], 69614642h; PoolTag
0x140012194  mov     [rsp+278h+EcpContextSize], 0; CleanupCallback
0x14001219d  xor     r9d, r9d; Flags
0x1400121a0  lea     rdx, GUID_ECP_CLOUDFILES_ATTRIBUTION; EcpType
0x1400121a7  mov     rcx, [r15+8]; Filter
0x1400121ab  call    cs:__imp_FltAllocateExtraCreateParameter
0x1400121b2  nop     dword ptr [rax+rax+00h]
0x1400121b7  mov     ebx, eax
0x1400121b9  mov     [rsp+278h+var_22C], eax
0x1400121bd  test    eax, eax
0x1400121bf  js      loc_1400123AE
0x1400121c5  mov     r8d, [rsp+278h+var_230]; Size
0x1400121ca  xor     edx, edx; Val
0x1400121cc  mov     rcx, [rsp+278h+EcpContext]; void *
0x1400121d1  call    memset
0x1400121d6  mov     rcx, [rsp+278h+EcpContext]
0x1400121db  mov     eax, [rsp+278h+var_230]
0x1400121df  mov     [rcx], eax
0x1400121e1  mov     r8, r14
0x1400121e4  mov     rdx, rdi
0x1400121e7  mov     rcx, [rsp+278h+EcpContext]
0x1400121ec  call    BfFillOutEcpFields
0x1400121f1  xor     ecx, ecx
0x1400121f3  mov     rax, [rsp+278h+EcpContext]
0x1400121f8  mov     [rax+3Ah], cx
0x1400121fc  mov     rcx, r13
0x1400121ff  shr     rcx, 1
0x140012202  mov     rax, [rsp+278h+EcpContext]
0x140012207  mov     [rax+3Ch], cx
0x14001220b  movzx   edx, cx
0x14001220e  inc     edx
0x140012210  mov     [rsp+278h+var_228], edx
0x140012214  mov     r8d, 0FFFFh
0x14001221a  cmp     edx, r8d
0x14001221d  jbe     short loc_14001222D
0x14001221f  mov     ebx, 0C000000Dh
0x140012224  mov     [rsp+278h+var_22C], ebx
0x140012228  jmp     loc_1400123AE
0x14001222d  mov     rax, [rsp+278h+EcpContext]
0x140012232  mov     [rax+3Eh], dx
0x140012236  mov     rcx, rsi
0x140012239  shr     rcx, 1
0x14001223c  mov     rax, [rsp+278h+EcpContext]
0x140012241  mov     [rax+40h], cx
0x140012245  mov     [rsp+278h+var_224], edx
0x140012249  movzx   eax, cx
0x14001224c  inc     eax
0x14001224e  add     edx, eax
0x140012250  mov     [rsp+278h+var_228], edx
0x140012254  cmp     edx, r8d
0x140012257  jbe     short loc_140012267
0x140012259  mov     ebx, 0C000000Dh
0x14001225e  mov     [rsp+278h+var_22C], ebx
0x140012262  jmp     loc_1400123AE
0x140012267  mov     rax, [rsp+278h+EcpContext]
0x14001226c  mov     [rax+42h], dx
0x140012270  mov     rcx, [rsp+278h+Size]
0x140012275  shr     rcx, 1
0x140012278  mov     rax, [rsp+278h+EcpContext]
0x14001227d  mov     [rax+44h], cx
0x140012281  mov     [rsp+278h+var_224], edx
0x140012285  movzx   ecx, cx
0x140012288  inc     ecx
0x14001228a  add     ecx, edx
0x14001228c  mov     [rsp+278h+var_228], ecx
0x140012290  cmp     ecx, r8d
0x140012293  jbe     short loc_1400122A3
0x140012295  mov     ebx, 0C000000Dh
0x14001229a  mov     [rsp+278h+var_22C], ebx
0x14001229e  jmp     loc_1400123AE
0x1400122a3  mov     rax, [rsp+278h+EcpContext]
0x1400122a8  mov     [rax+46h], cx
0x1400122ac  mov     rcx, [rsp+278h+var_218]
0x1400122b1  shr     rcx, 1
0x1400122b4  mov     rax, [rsp+278h+EcpContext]
0x1400122b9  mov     [rax+48h], cx
0x1400122bd  mov     rcx, [rsp+278h+EcpContext]
0x1400122c2  movzx   eax, word ptr [rcx+3Ah]
0x1400122c6  lea     rcx, [rcx+rax*2]
0x1400122ca  add     rcx, 4Ah ; 'J'; void *
0x1400122ce  mov     r8, r13; Size
0x1400122d1  mov     rdx, [rsp+278h+var_1F8+8]; Src
0x1400122d9  call    RtlCopyFromUser
0x1400122de  mov     rcx, [rsp+278h+EcpContext]
0x1400122e3  movzx   eax, word ptr [rcx+3Eh]
0x1400122e7  lea     rcx, [rcx+rax*2]
0x1400122eb  add     rcx, 4Ah ; 'J'; void *
0x1400122ef  mov     r8, rsi; Size
0x1400122f2  mov     rdx, [rsp+278h+var_1E8+8]; Src
0x1400122fa  call    RtlCopyFromUser
0x1400122ff  mov     rcx, [rsp+278h+EcpContext]
0x140012304  movzx   eax, word ptr [rcx+42h]
0x140012308  lea     rcx, [rcx+rax*2]
0x14001230c  add     rcx, 4Ah ; 'J'; void *
0x140012310  mov     r8, [rsp+278h+Size]; Size
0x140012315  lea     rdx, [rsp+278h+Src]; Src
0x14001231d  call    memmove
0x140012322  mov     rcx, [rsp+278h+EcpContext]
0x140012327  movzx   eax, word ptr [rcx+46h]
0x14001232b  lea     rcx, [rcx+rax*2]
0x14001232f  add     rcx, 4Ah ; 'J'; void *
0x140012333  mov     r8, [rsp+278h+var_218]; Size
0x140012338  lea     rdx, [rsp+278h+var_1D8]; Src
0x140012340  call    memmove
0x140012345  nop
0x140012346  mov     r8, [rsp+278h+EcpContext]; EcpContext
0x14001234b  mov     rdx, [rsp+278h+EcpList]; EcpList
0x140012350  mov     rcx, [r15+8]; Filter
0x140012354  call    cs:__imp_FltInsertExtraCreateParameter
0x14001235b  nop     dword ptr [rax+rax+00h]
0x140012360  mov     ebx, eax
0x140012362  test    eax, eax
0x140012364  jns     short loc_14001237D
0x140012366  mov     rdx, [rsp+278h+EcpContext]; EcpContext
0x14001236b  mov     rcx, [r15+8]; Filter
0x14001236f  call    cs:__imp_FltFreeExtraCreateParameter
0x140012376  nop     dword ptr [rax+rax+00h]
0x14001237b  jmp     short loc_1400123AE
0x14001237d  mov     byte ptr [r12], 1
0x140012382  jmp     short loc_1400123AE
0x140012384  mov     ebx, eax
0x140012386  mov     [rsp+278h+var_22C], eax
0x14001238a  mov     rdx, [rsp+278h+EcpContext]; EcpContext
0x14001238f  test    rdx, rdx
0x140012392  jz      short loc_1400123A9
0x140012394  mov     rcx, [rsp+278h+var_200]
0x140012399  mov     rcx, [rcx+8]; Filter
0x14001239d  call    cs:__imp_FltFreeExtraCreateParameter
0x1400123a4  nop     dword ptr [rax+rax+00h]
0x1400123a9  jmp     short loc_1400123AE
0x1400123ab  mov     ebx, r13d
0x1400123ae  mov     eax, ebx
0x1400123b0  mov     rcx, [rsp+278h+var_48]
0x1400123b8  xor     rcx, rsp; StackCookie
0x1400123bb  call    __security_check_cookie
0x1400123c0  add     rsp, 240h
0x1400123c7  pop     r15
0x1400123c9  pop     r14
0x1400123cb  pop     r13
0x1400123cd  pop     r12
0x1400123cf  pop     rdi
0x1400123d0  pop     rsi
0x1400123d1  pop     rbx
0x1400123d2  retn
```
