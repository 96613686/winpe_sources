# IsXboxLicensingUndocked

- ea: `0x18008e3a8`
- end: `0x18008e446`
- name: `IsXboxLicensingUndocked`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180054428`
- `0x18006547c`

## callees

- `0x180076e64`
- `0x18008221c`
- `0x180082284`
- `0x18008e3a8`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18008e3f8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18008e3f8`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x18008e41c`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x18008e41c`

## pseudocode

```c
char IsXboxLicensingUndocked()
{
  __int64 v0; // rcx
  char v1; // bl
  int v3; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18010C0A8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18010C0A8);
    if ( dword_18010C0A8 == -1 )
    {
      v3 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v3, 0);
      v1 = 1;
      if ( v3 != 5 && (unsigned int)(v3 - 11) > 1
        || !(unsigned __int8)IsCompareContentIdPresent(v0)
        || !(unsigned int)ShouldLicenseManagerServiceAutoStop() )
      {
        v1 = 0;
      }
      byte_18010C0AC = v1;
      Init_thread_footer(&dword_18010C0A8);
    }
  }
  return byte_18010C0AC;
}

```

## disassembly

```asm
0x18008e3a8  push    rbx
0x18008e3aa  sub     rsp, 20h
0x18008e3ae  mov     ecx, cs:_tls_index
0x18008e3b4  mov     rax, gs:58h
0x18008e3bd  mov     edx, 4
0x18008e3c2  mov     rax, [rax+rcx*8]
0x18008e3c6  mov     eax, [rdx+rax]
0x18008e3c9  cmp     cs:dword_18010C0A8, eax
0x18008e3cf  jle     short loc_18008E43A
0x18008e3d1  lea     rcx, dword_18010C0A8
0x18008e3d8  call    _Init_thread_header
0x18008e3dd  cmp     cs:dword_18010C0A8, 0FFFFFFFFh
0x18008e3e4  jnz     short loc_18008E43A
0x18008e3e6  xor     r8d, r8d
0x18008e3e9  mov     [rsp+28h+arg_0], 0
0x18008e3f1  lea     rdx, [rsp+28h+arg_0]
0x18008e3f6  xor     ecx, ecx
0x18008e3f8  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18008e3fe  mov     eax, [rsp+28h+arg_0]
0x18008e402  mov     ebx, 1
0x18008e407  cmp     eax, 5
0x18008e40a  jz      short loc_18008E413
0x18008e40c  add     eax, 0FFFFFFF5h
0x18008e40f  cmp     eax, ebx
0x18008e411  ja      short loc_18008E426
0x18008e413  call    IsCompareContentIdPresent
0x18008e418  test    al, al
0x18008e41a  jz      short loc_18008E426
0x18008e41c  call    cs:__imp_ShouldLicenseManagerServiceAutoStop
0x18008e422  test    eax, eax
0x18008e424  jnz     short loc_18008E428
0x18008e426  xor     bl, bl
0x18008e428  lea     rcx, dword_18010C0A8
0x18008e42f  mov     cs:byte_18010C0AC, bl
0x18008e435  call    _Init_thread_footer
0x18008e43a  mov     al, cs:byte_18010C0AC
0x18008e440  add     rsp, 20h
0x18008e444  pop     rbx
0x18008e445  retn
```
