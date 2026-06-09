# IPxlatSvcControl::GetInstance(void)

- ea: `0x18000c314`
- end: `0x18000c3c3`
- name: `?GetInstance@IPxlatSvcControl@@SAAEAV1@XZ`
- size: `175`
- prototype: `struct IPxlatSvcControl *(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c450`
- `0x18000c590`
- `0x18000c7d0`
- `0x18000ccd0`
- `0x18000ce30`

## callees

- `0x1800020f0`
- `0x1800022a0`
- `0x180002308`
- `0x18000c314`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000c3a0`
- `ntdll!RtlInitUnicodeString` at `0x18000c3a0`

## string_xrefs

- `0x18000c38b`: `\Registry\Machine\System\CurrentControlSet\Services\WinNat`

## pseudocode

```c
struct IPxlatSvcControl *IPxlatSvcControl::GetInstance(void)
{
  if ( __TSS0__1__GetInstance_IPxlatSvcControl__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + (unsigned int)tls_index)
                                                                           + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetInstance_IPxlatSvcControl__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetInstance_IPxlatSvcControl__SAAEAV2_XZ_4HA == -1 )
    {
      qword_180023958 = 0;
      qword_180023960 = 0;
      `IPxlatSvcControl::GetInstance'::`2'::Instance = 0;
      qword_180023938 = 0;
      qword_180023940 = 0;
      xmmword_180023918 = 0;
      *(__int128 *)((char *)&xmmword_180023918 + 12) = 0;
      RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\WinNat");
      atexit(`IPxlatSvcControl::GetInstance'::`2'::`dynamic atexit destructor for 'Instance'');
      Init_thread_footer(&__TSS0__1__GetInstance_IPxlatSvcControl__SAAEAV2_XZ_4HA);
    }
  }
  return (struct IPxlatSvcControl *)&`IPxlatSvcControl::GetInstance'::`2'::Instance;
}

```

## disassembly

```asm
0x18000c314  sub     rsp, 28h
0x18000c318  mov     ecx, cs:_tls_index
0x18000c31e  mov     rax, gs:58h
0x18000c327  mov     edx, 4
0x18000c32c  mov     rax, [rax+rcx*8]
0x18000c330  mov     eax, [rdx+rax]
0x18000c333  cmp     cs:?$TSS0@?1??GetInstance@IPxlatSvcControl@@SAAEAV2@XZ@4HA, eax
0x18000c339  jg      short loc_18000C347
0x18000c33b  lea     rax, ?Instance@?1??GetInstance@IPxlatSvcControl@@SAAEAV2@XZ@4V2@A; IPxlatSvcControl `IPxlatSvcControl::GetInstance(void)'::`2'::Instance
0x18000c342  add     rsp, 28h
0x18000c346  retn
0x18000c347  lea     rcx, ?$TSS0@?1??GetInstance@IPxlatSvcControl@@SAAEAV2@XZ@4HA
0x18000c34e  call    _Init_thread_header
0x18000c353  cmp     cs:?$TSS0@?1??GetInstance@IPxlatSvcControl@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18000c35a  jnz     short loc_18000C33B
0x18000c35c  xor     edx, edx
0x18000c35e  lea     rcx, DestinationString; DestinationString
0x18000c365  xorps   xmm0, xmm0
0x18000c368  mov     cs:qword_180023958, rdx
0x18000c36f  mov     cs:qword_180023960, rdx
0x18000c376  mov     cs:?Instance@?1??GetInstance@IPxlatSvcControl@@SAAEAV2@XZ@4V2@A, rdx; IPxlatSvcControl `IPxlatSvcControl::GetInstance(void)'::`2'::Instance
0x18000c37d  mov     cs:qword_180023938, rdx
0x18000c384  mov     cs:qword_180023940, rdx
0x18000c38b  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000c392  movups  cs:xmmword_180023918, xmm0
0x18000c399  movups  cs:xmmword_180023918+0Ch, xmm0
0x18000c3a0  call    cs:__imp_RtlInitUnicodeString
0x18000c3a6  lea     rcx, ??__FInstance@?1??GetInstance@IPxlatSvcControl@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18000c3ad  call    atexit
0x18000c3b2  lea     rcx, ?$TSS0@?1??GetInstance@IPxlatSvcControl@@SAAEAV2@XZ@4HA
0x18000c3b9  call    _Init_thread_footer
0x18000c3be  jmp     loc_18000C33B
```
