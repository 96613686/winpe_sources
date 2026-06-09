# FltpInitVolume

- ea: `0x180067db0`
- end: `0x1800681d3`
- name: `FltpInitVolume`
- size: `1059`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180067be0`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x18001bd90`
- `0x180024c40`
- `0x180067280`
- `0x180067db0`
- `0x180068e20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180067e07`
- `ntoskrnl!ExAllocatePool2` at `0x180067eb3`
- `ntoskrnl!ExAllocatePool2` at `0x180067e07`
- `ntoskrnl!ExAllocatePool2` at `0x180067eb3`
- `ntoskrnl!KeInitializeEvent` at `0x180068101`
- `ntoskrnl!KeInitializeEvent` at `0x180068101`
- `ntoskrnl!ObfReferenceObject` at `0x180067ee2`
- `ntoskrnl!ObfReferenceObject` at `0x180067ee2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006800d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006803c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180068068`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006800d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006803c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180068068`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180067fb8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180067fb8`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x1800680ae`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x180068149`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x1800680ae`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x180068149`
- `ntoskrnl!ExInitializeRundownProtection` at `0x180067e49`
- `ntoskrnl!ExInitializeRundownProtection` at `0x180067e49`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f01`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f2e`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f5b`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f81`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f01`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f2e`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f5b`
- `ntoskrnl!ExInitializeFastResource` at `0x180067f81`

## pseudocode

```c
__int64 __fastcall FltpInitVolume(
        __int64 a1,
        void *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        const UNICODE_STRING *String1,
        __int64 *a6)
{
  unsigned __int64 v8; // r10
  __int64 Pool2; // rax
  __int64 v11; // rbx
  __int64 result; // rax
  int v13; // r8d
  __int64 v14; // rax
  unsigned int i; // esi
  __int64 v16; // rax
  __int64 *v17; // rdi
  unsigned __int16 Length; // ax
  __int64 v19; // rdi
  unsigned __int16 v20; // ax
  __int64 v21; // rdi
  unsigned __int16 v22; // ax
  __int64 v23; // rdi
  unsigned int j; // edi
  unsigned int v25; // esi
  _BYTE v26[48]; // [rsp+20h] [rbp-38h]

  v8 = a4->Length + (unsigned __int64)a3->Length;
  *(_QWORD *)v26 = 0;
  *(_DWORD *)&v26[8] = 0;
  Pool2 = ExAllocatePool2(64, v8 + String1->Length + 2346LL, 1870024006);
  v11 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 0x4000000;
    *(_DWORD *)(Pool2 + 4) = 1;
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)(Pool2 + 8));
    v13 = *(_DWORD *)v11;
    *(_QWORD *)(v11 + 16) = 0;
    if ( (v13 & 0x2000000) != 0 && (FltGlobals[0] & 0x2000) != 0
      || (v13 & 0x4000000) != 0 && (FltGlobals[0] & 0x4000) != 0
      || (v13 & 0x1000000) != 0 && (FltGlobals[0] & 0x8000) != 0 )
    {
      v14 = ExAllocatePool2(64, 131080, 1819430214);
    }
    else
    {
      v14 = 0;
    }
    *(_QWORD *)(v11 + 32) = v14;
    *(_OWORD *)(v11 + 40) = 0;
    FltObjectReference((PVOID)v11);
    *(_QWORD *)(v11 + 64) = a1;
    *(_QWORD *)(v11 + 72) = a2;
    if ( a2 )
      ObfReferenceObject(a2);
    *(_DWORD *)(v11 + 312) = 0;
    ExInitializeFastResource(v11 + 192, 8);
    *(_QWORD *)(v11 + 304) = v11 + 296;
    *(_QWORD *)(v11 + 296) = v11 + 296;
    *(_DWORD *)(v11 + 1592) = 0;
    ExInitializeFastResource(v11 + 1472, 8);
    *(_QWORD *)(v11 + 1584) = v11 + 1576;
    *(_QWORD *)(v11 + 1576) = v11 + 1576;
    *(_DWORD *)(v11 + 1720) = 0;
    ExInitializeFastResource(v11 + 1600, 8);
    *(_QWORD *)(v11 + 1712) = v11 + 1704;
    *(_QWORD *)(v11 + 1704) = v11 + 1704;
    ExInitializeFastResource(v11 + 1928, 8);
    *(_DWORD *)(v11 + 60) = 0;
    for ( i = 0; ; ++i )
    {
      v16 = 4LL * i;
      v17 = &FsTypes[v16];
      if ( LODWORD(FsTypes[v16]) == -1 )
        break;
      if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)&qword_18003E060[v16], 1u) )
      {
        *(_DWORD *)(v11 + 60) = *(_DWORD *)v17;
        break;
      }
    }
    if ( *(_DWORD *)(a1 + 72) == 20 )
      *(_DWORD *)(v11 + 56) |= 1u;
    Length = a4->Length;
    *(_OWORD *)(v11 + 160) = 0;
    *(_WORD *)(v11 + 162) = Length;
    *(_QWORD *)(v11 + 168) = v11 + 2248;
    v19 = v11 + 2248 + a4->Length;
    RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 160), a4);
    v20 = String1->Length;
    *(_OWORD *)(v11 + 176) = 0;
    *(_QWORD *)(v11 + 184) = v19;
    *(_WORD *)(v11 + 178) = v20;
    v21 = String1->Length + v19;
    RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 176), String1);
    v22 = a3->Length;
    *(_OWORD *)(v11 + 112) = 0;
    *(_QWORD *)(v11 + 120) = v21;
    *(_WORD *)(v11 + 114) = v22;
    v23 = a3->Length + v21;
    RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 112), a3);
    *(_OWORD *)(v11 + 128) = 0;
    *(_WORD *)(v11 + 130) = 98;
    *(_QWORD *)(v11 + 136) = v23;
    FltpUpdateVolumeDosName(v11);
    *(_DWORD *)v26 = FltpInitVolumeCallbackEnvironment(v11);
    ExInitializeAutoExpandPushLock(v11 + 1320, 1);
    memset((void *)(v11 + 1336), 0, 0x80u);
    *(_QWORD *)(v11 + 1464) = 0;
    *(_QWORD *)&v26[4] = 0;
    *(_DWORD *)(v11 + 1728) = 1;
    *(_QWORD *)(v11 + 1736) = 0;
    *(_DWORD *)(v11 + 1744) = 0;
    KeInitializeEvent((PRKEVENT)(v11 + 1752), SynchronizationEvent, 0);
    *(_DWORD *)(v11 + 1784) = 0;
    *(_QWORD *)(v11 + 1792) = 0;
    *(_QWORD *)(v11 + 1800) = 0;
    memset((void *)(v11 + 1808), 0, 0x78u);
    *(_QWORD *)(v11 + 2056) = 0;
    ExInitializeAutoExpandPushLock(v11 + 2040, 1);
    for ( j = 0; j < 3; ++j )
    {
      v25 = *(_DWORD *)&v26[4 * j];
      if ( (int)FltpDbgStatus(v25, "minkernel\\fs\\filtermgr\\filter\\volumesup.c", 360, 0) < 0 )
      {
        FltpFreeVolume((char *)v11);
        result = v25;
        *a6 = 0;
        return result;
      }
    }
    *(_QWORD *)(v11 + 104) = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL);
    *a6 = v11;
    return 0;
  }
  else
  {
    *a6 = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x180067db0  mov     [rsp+arg_8], rbx
0x180067db5  mov     [rsp+SourceString], r8
0x180067dba  push    rdi
0x180067dbb  push    r12
0x180067dbd  push    r13
0x180067dbf  push    r14
0x180067dc1  push    r15
0x180067dc3  sub     rsp, 30h
0x180067dc7  movzx   r10d, word ptr [r8]
0x180067dcb  mov     rdi, rdx
0x180067dce  movzx   eax, word ptr [r9]
0x180067dd2  mov     r13, rcx
0x180067dd5  mov     r15, [rsp+58h+String1]
0x180067ddd  xor     ecx, ecx
0x180067ddf  add     r10, rax
0x180067de2  mov     [rsp+58h+var_38], rcx
0x180067de7  mov     [rsp+58h+var_30], ecx
0x180067deb  mov     r8d, 6F764D46h
0x180067df1  mov     ecx, 40h ; '@'
0x180067df6  mov     r12, r9
0x180067df9  movzx   edx, word ptr [r15]
0x180067dfd  add     rdx, 92Ah
0x180067e04  add     rdx, r10
0x180067e07  call    cs:__imp_ExAllocatePool2
0x180067e0e  nop     dword ptr [rax+rax+00h]
0x180067e13  mov     rbx, rax
0x180067e16  test    rax, rax
0x180067e19  jnz     short loc_180067E33
0x180067e1b  mov     rax, [rsp+58h+arg_28]
0x180067e23  xor     r14d, r14d
0x180067e26  mov     [rax], r14
0x180067e29  mov     eax, 0C000009Ah
0x180067e2e  jmp     loc_1800681BF
0x180067e33  lea     rcx, [rax+8]; RunRef
0x180067e37  mov     [rsp+58h+arg_0], rsi
0x180067e3c  mov     dword ptr [rax], 4000000h
0x180067e42  mov     dword ptr [rax+4], 1
0x180067e49  call    cs:__imp_ExInitializeRundownProtection
0x180067e50  nop     dword ptr [rax+rax+00h]
0x180067e55  mov     r8d, [rbx]
0x180067e58  xor     r14d, r14d
0x180067e5b  bt      r8d, 19h
0x180067e60  mov     [rbx+10h], r14
0x180067e64  mov     edx, cs:FltGlobals
0x180067e6a  setb    cl
0x180067e6d  bt      edx, 0Dh
0x180067e71  setb    al
0x180067e74  test    al, cl
0x180067e76  jnz     short loc_180067EA3
0x180067e78  bt      r8d, 1Ah
0x180067e7d  setb    cl
0x180067e80  bt      edx, 0Eh
0x180067e84  setb    al
0x180067e87  test    al, cl
0x180067e89  jnz     short loc_180067EA3
0x180067e8b  bt      r8d, 18h
0x180067e90  setb    cl
0x180067e93  bt      edx, 0Fh
0x180067e97  setb    al
0x180067e9a  test    al, cl
0x180067e9c  jnz     short loc_180067EA3
0x180067e9e  mov     eax, r14d
0x180067ea1  jmp     short loc_180067EBF
0x180067ea3  mov     edx, 20008h
0x180067ea8  mov     ecx, 40h ; '@'
0x180067ead  mov     r8d, 6C724D46h
0x180067eb3  call    cs:__imp_ExAllocatePool2
0x180067eba  nop     dword ptr [rax+rax+00h]
0x180067ebf  xorps   xmm0, xmm0
0x180067ec2  mov     [rbx+20h], rax
0x180067ec6  mov     rcx, rbx; FltObject
0x180067ec9  movups  xmmword ptr [rbx+28h], xmm0
0x180067ecd  call    FltObjectReference
0x180067ed2  mov     [rbx+40h], r13
0x180067ed6  mov     [rbx+48h], rdi
0x180067eda  test    rdi, rdi
0x180067edd  jz      short loc_180067EEE
0x180067edf  mov     rcx, rdi; Object
0x180067ee2  call    cs:__imp_ObfReferenceObject
0x180067ee9  nop     dword ptr [rax+rax+00h]
0x180067eee  mov     edx, 8
0x180067ef3  mov     [rbx+138h], r14d
0x180067efa  lea     rcx, [rbx+0C0h]
0x180067f01  call    cs:__imp_ExInitializeFastResource
0x180067f08  nop     dword ptr [rax+rax+00h]
0x180067f0d  lea     rax, [rbx+128h]
0x180067f14  mov     edx, 8
0x180067f19  mov     [rax+8], rax
0x180067f1d  lea     rcx, [rbx+5C0h]
0x180067f24  mov     [rax], rax
0x180067f27  mov     [rbx+638h], r14d
0x180067f2e  call    cs:__imp_ExInitializeFastResource
0x180067f35  nop     dword ptr [rax+rax+00h]
0x180067f3a  lea     rax, [rbx+628h]
0x180067f41  mov     edx, 8
0x180067f46  mov     [rax+8], rax
0x180067f4a  lea     rcx, [rbx+640h]
0x180067f51  mov     [rax], rax
0x180067f54  mov     [rbx+6B8h], r14d
0x180067f5b  call    cs:__imp_ExInitializeFastResource
0x180067f62  nop     dword ptr [rax+rax+00h]
0x180067f67  lea     rax, [rbx+6A8h]
0x180067f6e  mov     edx, 8
0x180067f73  lea     rcx, [rbx+788h]
0x180067f7a  mov     [rax+8], rax
0x180067f7e  mov     [rax], rax
0x180067f81  call    cs:__imp_ExInitializeFastResource
0x180067f88  nop     dword ptr [rax+rax+00h]
0x180067f8d  mov     [rbx+3Ch], r14d
0x180067f91  mov     esi, r14d
0x180067f94  mov     eax, esi
0x180067f96  lea     rcx, FsTypes
0x180067f9d  shl     rax, 5
0x180067fa1  cmp     dword ptr [rax+rcx], 0FFFFFFFFh
0x180067fa5  lea     rdi, [rax+rcx]
0x180067fa9  jz      short loc_180067FD1
0x180067fab  lea     rdx, [rcx+10h]
0x180067faf  mov     r8b, 1; CaseInSensitive
0x180067fb2  add     rdx, rax; String2
0x180067fb5  mov     rcx, r15; String1
0x180067fb8  call    cs:__imp_RtlEqualUnicodeString
0x180067fbf  nop     dword ptr [rax+rax+00h]
0x180067fc4  test    al, al
0x180067fc6  jnz     short loc_180067FCC
0x180067fc8  inc     esi
0x180067fca  jmp     short loc_180067F94
0x180067fcc  mov     eax, [rdi]
0x180067fce  mov     [rbx+3Ch], eax
0x180067fd1  cmp     dword ptr [r13+48h], 14h
0x180067fd6  jnz     short loc_180067FE1
0x180067fd8  mov     eax, [rbx+38h]
0x180067fdb  or      eax, 1
0x180067fde  mov     [rbx+38h], eax
0x180067fe1  movzx   eax, word ptr [r12]
0x180067fe6  lea     rcx, [rbx+0A0h]; DestinationString
0x180067fed  lea     r8, [rbx+8C8h]
0x180067ff4  xorps   xmm0, xmm0
0x180067ff7  movups  xmmword ptr [rcx], xmm0
0x180067ffa  mov     [rcx+2], ax
0x180067ffe  mov     rdx, r12; SourceString
0x180068001  mov     [rcx+8], r8
0x180068005  movzx   edi, word ptr [r12]
0x18006800a  add     rdi, r8
0x18006800d  call    cs:__imp_RtlCopyUnicodeString
0x180068014  nop     dword ptr [rax+rax+00h]
0x180068019  movzx   eax, word ptr [r15]
0x18006801d  lea     rcx, [rbx+0B0h]; DestinationString
0x180068024  xorps   xmm0, xmm0
0x180068027  mov     rdx, r15; SourceString
0x18006802a  movups  xmmword ptr [rcx], xmm0
0x18006802d  mov     [rcx+8], rdi
0x180068031  mov     [rcx+2], ax
0x180068035  movzx   eax, word ptr [r15]
0x180068039  add     rdi, rax
0x18006803c  call    cs:__imp_RtlCopyUnicodeString
0x180068043  nop     dword ptr [rax+rax+00h]
0x180068048  mov     rdx, [rsp+58h+SourceString]; SourceString
0x18006804d  lea     rcx, [rbx+70h]; DestinationString
0x180068051  xorps   xmm0, xmm0
0x180068054  movzx   eax, word ptr [rdx]
0x180068057  movups  xmmword ptr [rcx], xmm0
0x18006805a  mov     [rcx+8], rdi
0x18006805e  mov     [rcx+2], ax
0x180068062  movzx   eax, word ptr [rdx]
0x180068065  add     rdi, rax
0x180068068  call    cs:__imp_RtlCopyUnicodeString
0x18006806f  nop     dword ptr [rax+rax+00h]
0x180068074  xorps   xmm0, xmm0
0x180068077  mov     rcx, rbx
0x18006807a  movups  xmmword ptr [rbx+80h], xmm0
0x180068081  mov     word ptr [rbx+82h], 62h ; 'b'
0x18006808a  mov     [rbx+88h], rdi
0x180068091  call    FltpUpdateVolumeDosName
0x180068096  mov     rcx, rbx
0x180068099  call    FltpInitVolumeCallbackEnvironment
0x18006809e  mov     edx, 1
0x1800680a3  mov     dword ptr [rsp+58h+var_38], eax
0x1800680a7  lea     rcx, [rbx+528h]
0x1800680ae  call    cs:__imp_ExInitializeAutoExpandPushLock
0x1800680b5  nop     dword ptr [rax+rax+00h]
0x1800680ba  xor     edx, edx; Val
0x1800680bc  lea     rcx, [rbx+538h]; void *
0x1800680c3  mov     r8d, 80h; Size
0x1800680c9  call    memset
0x1800680ce  mov     [rbx+5B8h], r14
0x1800680d5  lea     rcx, [rbx+6D8h]; Event
0x1800680dc  xor     r8d, r8d; State
0x1800680df  mov     [rsp+58h+var_38+4], r14
0x1800680e4  mov     edx, 1; Type
0x1800680e9  mov     dword ptr [rbx+6C0h], 1
0x1800680f3  mov     [rbx+6C8h], r14
0x1800680fa  mov     [rbx+6D0h], r14d
0x180068101  call    cs:__imp_KeInitializeEvent
0x180068108  nop     dword ptr [rax+rax+00h]
0x18006810d  lea     rcx, [rbx+710h]; void *
0x180068114  mov     [rbx+6F8h], r14d
0x18006811b  xor     edx, edx; Val
0x18006811d  mov     [rbx+700h], r14
0x180068124  mov     r8d, 78h ; 'x'; Size
0x18006812a  mov     [rbx+708h], r14
0x180068131  call    memset
0x180068136  lea     rcx, [rbx+7F8h]
0x18006813d  mov     [rbx+808h], r14
0x180068144  mov     edx, 1
0x180068149  call    cs:__imp_ExInitializeAutoExpandPushLock
0x180068150  nop     dword ptr [rax+rax+00h]
0x180068155  mov     edi, r14d
0x180068158  mov     r15d, 168h
0x18006815e  cmp     edi, 3
0x180068161  jnb     short loc_1800681A1
0x180068163  mov     eax, edi
0x180068165  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x18006816c  xor     r9d, r9d
0x18006816f  mov     r8d, r15d
0x180068172  mov     esi, dword ptr [rsp+rax*4+58h+var_38]
0x180068176  mov     ecx, esi
0x180068178  call    FltpDbgStatus
0x18006817d  test    eax, eax
0x18006817f  js      short loc_180068185
0x180068181  inc     edi
0x180068183  jmp     short loc_18006815E
0x180068185  mov     edx, 10h
0x18006818a  mov     rcx, rbx; OwnerId
0x18006818d  call    FltpFreeVolume
0x180068192  mov     rcx, [rsp+58h+arg_28]
0x18006819a  mov     eax, esi
0x18006819c  mov     [rcx], r14
0x18006819f  jmp     short loc_1800681BA
0x1800681a1  mov     rax, [r13+40h]
0x1800681a5  mov     rcx, [rax+10h]
0x1800681a9  mov     rax, [rsp+58h+arg_28]
0x1800681b1  mov     [rbx+68h], rcx
0x1800681b5  mov     [rax], rbx
0x1800681b8  xor     eax, eax
0x1800681ba  mov     rsi, [rsp+58h+arg_0]
0x1800681bf  mov     rbx, [rsp+58h+arg_8]
0x1800681c4  add     rsp, 30h
0x1800681c8  pop     r15
0x1800681ca  pop     r14
0x1800681cc  pop     r13
0x1800681ce  pop     r12
0x1800681d0  pop     rdi
0x1800681d1  retn
```
