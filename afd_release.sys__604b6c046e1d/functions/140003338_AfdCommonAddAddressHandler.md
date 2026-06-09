# AfdCommonAddAddressHandler

- ea: `0x140003338`
- end: `0x1400035ba`
- name: `AfdCommonAddAddressHandler`
- size: `642`
- prototype: `void __fastcall(__int64, _QWORD *, _WORD *, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002a90`
- `0x140002d20`

## callees

- `0x140002ad4`
- `0x140003338`
- `0x1400035c0`
- `0x140003670`
- `0x1400036ac`
- `0x14003ff74`
- `0x140072800`
- `0x1400932cc`
- `0x140093a70`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14000336c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14000336c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003485`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400034e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003523`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003485`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400034e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003523`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003388`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003388`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003415`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003415`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140003498`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400034f3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140003536`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140003498`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400034f3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140003536`

## pseudocode

```c
void __fastcall AfdCommonAddAddressHandler(__int64 a1, _QWORD *a2, _WORD *a3, const UNICODE_STRING *a4)
{
  __int64 PoolPriority; // rax
  __int64 v9; // rsi
  __int64 *v10; // rcx
  bool v11; // r14
  __int16 v12; // ax
  int v13; // ecx
  int v14; // r8d

  AfdLastRemovedPdo = 0;
  if ( a4 )
  {
    ExEnterCriticalRegionAndAcquireResourceShared(AfdGlobalData);
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 192), 1u);
    if ( AfdFindAddressInList(a1, a3, a2, a4) )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(a1 + 192));
      ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
    }
    else
    {
      PoolPriority = AfdAllocatePoolPriority(
                       256,
                       a4->MaximumLength + (((unsigned __int16)*a3 + 45LL) & 0xFFFFFFFFFFFFFFFEuLL),
                       1952736833,
                       32);
      v9 = PoolPriority;
      if ( PoolPriority )
      {
        memmove((void *)(PoolPriority + 40), a3, (unsigned __int16)*a3 + 4LL);
        *(_WORD *)(v9 + 26) = a4->MaximumLength;
        *(_QWORD *)(v9 + 32) = (v9 + (unsigned __int16)*a3 + 45LL) & 0xFFFFFFFFFFFFFFFEuLL;
        RtlCopyUnicodeString((PUNICODE_STRING)(v9 + 24), a4);
        *(_QWORD *)(v9 + 16) = *a2;
        v10 = *(__int64 **)(a1 + 176);
        if ( *v10 != a1 + 168 )
          __fastfail(3u);
        *(_QWORD *)v9 = a1 + 168;
        v11 = 0;
        *(_QWORD *)(v9 + 8) = v10;
        *v10 = v9;
        *(_QWORD *)(a1 + 176) = v9;
        v12 = a3[1];
        if ( v12 == 2 || v12 == 23 )
          v11 = ++*(_DWORD *)(a1 + 184) == 1;
        if ( (__int64 *)AfdEndpointListHead != &AfdEndpointListHead || AfdWskInitialized )
          AfdProcessAddressChangeList(a1, (unsigned __int16)a3[1], a4);
        ExReleaseResourceLite(*(PERESOURCE *)(a1 + 192));
        ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
        if ( v11 )
          AfdNotifyIPAvailabilityConsumers(1, *(_DWORD *)(a1 + 16));
      }
      else
      {
        ExReleaseResourceLite(*(PERESOURCE *)(a1 + 192));
        ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
        AfdHandleAddressChangeFailure(a1);
      }
      if ( (BYTE2(xmmword_1400875E0) & 2) != 0 )
        WPP_SF_dldZ(v13, 35, v14, (unsigned __int16)a3[1], *(_DWORD *)(a1 + 16), *a3, (__int64)a4);
    }
  }
  else if ( (BYTE2(xmmword_1400875D0) & 2) != 0 )
  {
    WPP_SF_d(529, 34, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, (unsigned __int16)a3[1]);
  }
}

```

## disassembly

```asm
0x140003338  push    rbx
0x14000333a  push    rbp
0x14000333b  push    rsi
0x14000333c  push    rdi
0x14000333d  push    r14
0x14000333f  push    r15
0x140003341  sub     rsp, 48h
0x140003345  mov     cs:AfdLastRemovedPdo, 0
0x140003350  mov     rbp, r9
0x140003353  mov     rdi, r8
0x140003356  mov     r14, rdx
0x140003359  mov     rbx, rcx
0x14000335c  test    r9, r9
0x14000335f  jz      loc_140003556
0x140003365  mov     rcx, cs:AfdGlobalData; Resource
0x14000336c  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x140003373  nop     dword ptr [rax+rax+00h]
0x140003378  mov     rcx, [rbx+0C0h]; Resource
0x14000337f  mov     r15d, 1
0x140003385  mov     dl, r15b; Wait
0x140003388  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000338f  nop     dword ptr [rax+rax+00h]
0x140003394  mov     r9, rbp
0x140003397  mov     r8, r14
0x14000339a  mov     rdx, rdi
0x14000339d  mov     rcx, rbx
0x1400033a0  call    AfdFindAddressInList
0x1400033a5  test    rax, rax
0x1400033a8  jnz     loc_1400034D9
0x1400033ae  movzx   edx, word ptr [rdi]
0x1400033b1  lea     r9d, [r15+1Fh]
0x1400033b5  movzx   eax, word ptr [rbp+2]
0x1400033b9  add     rdx, 2Dh ; '-'
0x1400033bd  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1400033c1  mov     ecx, 100h
0x1400033c6  add     rdx, rax
0x1400033c9  mov     r8d, 74646641h
0x1400033cf  call    AfdAllocatePoolPriority
0x1400033d4  mov     rsi, rax
0x1400033d7  test    rax, rax
0x1400033da  jz      loc_14000351C
0x1400033e0  movzx   r8d, word ptr [rdi]
0x1400033e4  lea     rcx, [rax+28h]; void *
0x1400033e8  add     r8, 4; Size
0x1400033ec  mov     rdx, rdi; Src
0x1400033ef  call    memmove
0x1400033f4  movzx   ecx, word ptr [rbp+2]
0x1400033f8  mov     [rsi+1Ah], cx
0x1400033fc  lea     rcx, [rsi+18h]; DestinationString
0x140003400  movzx   edx, word ptr [rdi]
0x140003403  add     rdx, 2Dh ; '-'
0x140003407  add     rdx, rsi
0x14000340a  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14000340e  mov     [rsi+20h], rdx
0x140003412  mov     rdx, rbp; SourceString
0x140003415  call    cs:__imp_RtlCopyUnicodeString
0x14000341c  nop     dword ptr [rax+rax+00h]
0x140003421  mov     rax, [r14]
0x140003424  mov     [rsi+10h], rax
0x140003428  lea     rax, [rbx+0A8h]
0x14000342f  mov     rcx, [rax+8]
0x140003433  cmp     [rcx], rax
0x140003436  jnz     loc_14000354F
0x14000343c  mov     [rsi], rax
0x14000343f  xor     r14b, r14b
0x140003442  mov     [rsi+8], rcx
0x140003446  mov     [rcx], rsi
0x140003449  mov     [rax+8], rsi
0x14000344d  movzx   eax, word ptr [rdi+2]
0x140003451  cmp     ax, 2
0x140003455  jz      loc_140003501
0x14000345b  cmp     ax, 17h
0x14000345f  jz      loc_140003501
0x140003465  lea     rax, AfdEndpointListHead
0x14000346c  cmp     cs:AfdEndpointListHead, rax
0x140003473  jnz     short loc_1400034C8
0x140003475  cmp     cs:AfdWskInitialized, 0
0x14000347c  jnz     short loc_1400034C8
0x14000347e  mov     rcx, [rbx+0C0h]; Resource
0x140003485  call    cs:__imp_ExReleaseResourceLite
0x14000348c  nop     dword ptr [rax+rax+00h]
0x140003491  mov     rcx, cs:AfdGlobalData; Resource
0x140003498  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000349f  nop     dword ptr [rax+rax+00h]
0x1400034a4  test    r14b, r14b
0x1400034a7  jnz     loc_140003583
0x1400034ad  test    byte ptr cs:xmmword_1400875E0+2, 2
0x1400034b4  jnz     loc_140003593
0x1400034ba  add     rsp, 48h
0x1400034be  pop     r15
0x1400034c0  pop     r14
0x1400034c2  pop     rdi
0x1400034c3  pop     rsi
0x1400034c4  pop     rbp
0x1400034c5  pop     rbx
0x1400034c6  retn
0x1400034c8  movzx   edx, word ptr [rdi+2]
0x1400034cc  mov     r8, rbp
0x1400034cf  mov     rcx, rbx
0x1400034d2  call    AfdProcessAddressChangeList
0x1400034d7  jmp     short loc_14000347E
0x1400034d9  mov     rcx, [rbx+0C0h]; Resource
0x1400034e0  call    cs:__imp_ExReleaseResourceLite
0x1400034e7  nop     dword ptr [rax+rax+00h]
0x1400034ec  mov     rcx, cs:AfdGlobalData; Resource
0x1400034f3  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400034fa  nop     dword ptr [rax+rax+00h]
0x1400034ff  jmp     short loc_1400034BA
0x140003501  add     [rbx+0B8h], r15d
0x140003508  cmp     [rbx+0B8h], r15d
0x14000350f  movzx   r14d, r14b
0x140003513  cmovz   r14d, r15d
0x140003517  jmp     loc_140003465
0x14000351c  mov     rcx, [rbx+0C0h]; Resource
0x140003523  call    cs:__imp_ExReleaseResourceLite
0x14000352a  nop     dword ptr [rax+rax+00h]
0x14000352f  mov     rcx, cs:AfdGlobalData; Resource
0x140003536  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000353d  nop     dword ptr [rax+rax+00h]
0x140003542  mov     rcx, rbx
0x140003545  call    AfdHandleAddressChangeFailure
0x14000354a  jmp     loc_1400034AD
0x14000354f  mov     ecx, 3
0x140003554  int     29h; Win8: RtlFailFast(ecx)
0x140003556  test    byte ptr cs:xmmword_1400875D0+2, 2
0x14000355d  jz      loc_1400034BA
0x140003563  movzx   r9d, word ptr [r8+2]
0x140003568  mov     edx, 22h ; '"'
0x14000356d  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x140003574  mov     ecx, 211h
0x140003579  call    WPP_SF_d
0x14000357e  jmp     loc_1400034BA
0x140003583  mov     edx, [rbx+10h]
0x140003586  mov     cl, r15b
0x140003589  call    AfdNotifyIPAvailabilityConsumers
0x14000358e  jmp     loc_1400034AD
0x140003593  movzx   eax, word ptr [rdi]
0x140003596  mov     edx, 23h ; '#'
0x14000359b  movzx   r9d, word ptr [rdi+2]
0x1400035a0  mov     [rsp+78h+var_48], rbp
0x1400035a5  mov     [rsp+78h+var_50], eax
0x1400035a9  mov     eax, [rbx+10h]
0x1400035ac  mov     [rsp+78h+var_58], eax
0x1400035b0  call    WPP_SF_dldZ
0x1400035b5  jmp     loc_1400034BA
```
