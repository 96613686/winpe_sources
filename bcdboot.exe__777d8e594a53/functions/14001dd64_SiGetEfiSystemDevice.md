# SiGetEfiSystemDevice

- ea: `0x14001dd64`
- end: `0x14001df10`
- name: `SiGetEfiSystemDevice`
- size: `428`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140013484`

## callees

- `0x14001c844`
- `0x14001db54`
- `0x14001dca0`
- `0x14001dd64`
- `0x14001df18`
- `0x140020ba4`
- `0x140026650`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001dd9b`
- `ntdll!RtlAllocateHeap` at `0x14001dd9b`
- `ntdll!RtlFreeHeap` at `0x14001ddd9`
- `ntdll!RtlFreeHeap` at `0x14001de87`
- `ntdll!RtlFreeHeap` at `0x14001ddd9`
- `ntdll!RtlFreeHeap` at `0x14001de87`

## string_xrefs

- `0x14001deca`: `Disambiguation successful. Device Path: %ws`
- `0x14001def4`: `System Device Path Found. Device Path: %ws`
- `0x14001de64`: `Attempting Disambiguation of system device. Found %lu ESP partitions and %lu Virtual ESP partitions.`

## pseudocode

```c
__int64 __fastcall SiGetEfiSystemDevice(__int64 a1, __int64 a2, _QWORD *a3)
{
  PVOID Heap; // rbx
  __int64 v5; // r8
  int v6; // r9d
  int v7; // edi
  __int64 v9; // rcx
  int EspFromFirmware; // eax
  void *v11; // [rsp+30h] [rbp-28h] BYREF
  __int128 v12; // [rsp+38h] [rbp-20h] BYREF

  v12 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x6Au);
  if ( !Heap )
  {
    v7 = -1073741801;
    goto LABEL_3;
  }
  v7 = SiDisambiguateSystemDevice((_DWORD *)&v12 + 2, (_DWORD *)&v12 + 3, v5, v6);
  if ( v7 >= 0 )
  {
    SiLogMessage(2, L"Found stored disambiguated system device to disk %lu, partition %lu.", DWORD2(v12), HIDWORD(v12));
LABEL_17:
    RtlStringCbPrintfW(Heap, 106, L"\\Device\\Harddisk%lu\\Partition%lu", DWORD2(v12), HIDWORD(v12));
    SiLogMessage(2, L"System Device Path Found. Device Path: %ws", Heap);
    goto LABEL_18;
  }
  v7 = SyspartEnumerateDisks(SyspartResolveEfiEspCallback, &v12);
  if ( v7 >= 0 )
  {
    if ( (_DWORD)v12 )
    {
      if ( (unsigned int)v12 <= 1 || DWORD1(v12) == 1 )
      {
        v7 = 0;
        goto LABEL_17;
      }
      SiLogMessage(
        3,
        L"Attempting Disambiguation of system device. Found %lu ESP partitions and %lu Virtual ESP partitions.");
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v11 = 0;
      EspFromFirmware = SiGetEspFromFirmware(v9, &v11);
      v7 = EspFromFirmware;
      if ( EspFromFirmware >= 0 )
      {
        Heap = v11;
        SiLogMessage(2, L"Disambiguation successful. Device Path: %ws", v11);
LABEL_18:
        *a3 = Heap;
        return (unsigned int)v7;
      }
      SiLogMessage(4, L"Disambiguation of system device failed. Status: %x", (unsigned int)EspFromFirmware);
      Heap = v11;
      v7 = -1073740719;
    }
    else
    {
      v7 = -1073740718;
    }
  }
LABEL_3:
  SiLogMessage(4, L"GetEfiSystemDevice Failed. Status: %x", (unsigned int)v7);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001dd64  push    rbp
0x14001dd66  push    rbx
0x14001dd67  push    rsi
0x14001dd68  push    rdi
0x14001dd69  mov     rbp, rsp
0x14001dd6c  sub     rsp, 58h
0x14001dd70  mov     rax, cs:__security_cookie
0x14001dd77  xor     rax, rsp
0x14001dd7a  mov     [rbp+var_10], rax
0x14001dd7e  xorps   xmm0, xmm0
0x14001dd81  xor     edx, edx; Flags
0x14001dd83  movups  [rbp+var_20], xmm0
0x14001dd87  mov     rcx, gs:60h
0x14001dd90  mov     rsi, r8
0x14001dd93  lea     r8d, [rdx+6Ah]; Size
0x14001dd97  mov     rcx, [rcx+30h]; HeapHandle
0x14001dd9b  call    cs:__imp_RtlAllocateHeap
0x14001dda1  mov     rbx, rax
0x14001dda4  test    rax, rax
0x14001dda7  jnz     short loc_14001DDF6
0x14001dda9  mov     edi, 0C0000017h
0x14001ddae  mov     r8d, edi
0x14001ddb1  lea     rdx, aGetefisystemde; "GetEfiSystemDevice Failed. Status: %x"
0x14001ddb8  mov     ecx, 4
0x14001ddbd  call    SiLogMessage
0x14001ddc2  test    rbx, rbx
0x14001ddc5  jz      short loc_14001DDDF
0x14001ddc7  mov     rcx, gs:60h
0x14001ddd0  mov     r8, rbx; P
0x14001ddd3  xor     edx, edx; Flags
0x14001ddd5  mov     rcx, [rcx+30h]; HeapHandle
0x14001ddd9  call    cs:__imp_RtlFreeHeap
0x14001dddf  mov     eax, edi
0x14001dde1  mov     rcx, [rbp+var_10]
0x14001dde5  xor     rcx, rsp; StackCookie
0x14001dde8  call    __security_check_cookie
0x14001dded  add     rsp, 58h
0x14001ddf1  pop     rdi
0x14001ddf2  pop     rsi
0x14001ddf3  pop     rbx
0x14001ddf4  pop     rbp
0x14001ddf5  retn
0x14001ddf6  lea     rdx, [rbp+var_20+0Ch]
0x14001ddfa  lea     rcx, [rbp+var_20+8]
0x14001ddfe  call    SiDisambiguateSystemDevice
0x14001de03  mov     edi, eax
0x14001de05  test    eax, eax
0x14001de07  js      short loc_14001DE27
0x14001de09  mov     r9d, dword ptr [rbp+var_20+0Ch]
0x14001de0d  lea     rdx, aFoundStoredDis; "Found stored disambiguated system devic"...
0x14001de14  mov     r8d, dword ptr [rbp+var_20+8]
0x14001de18  mov     ecx, 2
0x14001de1d  call    SiLogMessage
0x14001de22  jmp     loc_14001DED5
0x14001de27  lea     rdx, [rbp+var_20]
0x14001de2b  lea     rcx, SyspartResolveEfiEspCallback
0x14001de32  call    SyspartEnumerateDisks
0x14001de37  mov     edi, eax
0x14001de39  test    eax, eax
0x14001de3b  js      loc_14001DDAE
0x14001de41  mov     r8d, dword ptr [rbp+var_20]
0x14001de45  test    r8d, r8d
0x14001de48  jnz     short loc_14001DE54
0x14001de4a  mov     edi, 0C0000452h
0x14001de4f  jmp     loc_14001DDAE
0x14001de54  cmp     r8d, 1
0x14001de58  jbe     short loc_14001DED3
0x14001de5a  mov     r9d, dword ptr [rbp+var_20+4]
0x14001de5e  cmp     r9d, 1
0x14001de62  jz      short loc_14001DED3
0x14001de64  lea     rdx, aAttemptingDisa; "Attempting Disambiguation of system dev"...
0x14001de6b  mov     ecx, 3
0x14001de70  call    SiLogMessage
0x14001de75  mov     rcx, gs:60h
0x14001de7e  mov     r8, rbx; P
0x14001de81  xor     edx, edx; Flags
0x14001de83  mov     rcx, [rcx+30h]; HeapHandle
0x14001de87  call    cs:__imp_RtlFreeHeap
0x14001de8d  lea     rdx, [rbp+var_28]
0x14001de91  mov     [rbp+var_28], 0
0x14001de99  call    SiGetEspFromFirmware
0x14001de9e  mov     edi, eax
0x14001dea0  test    eax, eax
0x14001dea2  jns     short loc_14001DEC6
0x14001dea4  mov     r8d, eax
0x14001dea7  lea     rdx, aDisambiguation; "Disambiguation of system device failed."...
0x14001deae  mov     ecx, 4
0x14001deb3  call    SiLogMessage
0x14001deb8  mov     rbx, [rbp+var_28]
0x14001debc  mov     edi, 0C0000451h
0x14001dec1  jmp     loc_14001DDAE
0x14001dec6  mov     rbx, [rbp+var_28]
0x14001deca  lea     rdx, aDisambiguation_0; "Disambiguation successful. Device Path:"...
0x14001ded1  jmp     short loc_14001DEFB
0x14001ded3  xor     edi, edi
0x14001ded5  mov     eax, dword ptr [rbp+var_20+0Ch]
0x14001ded8  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition%lu"
0x14001dedf  mov     r9d, dword ptr [rbp+var_20+8]
0x14001dee3  mov     edx, 6Ah ; 'j'
0x14001dee8  mov     rcx, rbx
0x14001deeb  mov     [rsp+58h+var_38], eax
0x14001deef  call    RtlStringCbPrintfW
0x14001def4  lea     rdx, aSystemDevicePa; "System Device Path Found. Device Path: "...
0x14001defb  mov     r8, rbx
0x14001defe  mov     ecx, 2
0x14001df03  call    SiLogMessage
0x14001df08  mov     [rsi], rbx
0x14001df0b  jmp     loc_14001DDDF
```
