# IsXboxLicensingUndocked

- ea: `0x1800060f4`
- end: `0x180006192`
- name: `IsXboxLicensingUndocked`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800053b0`
- `0x180005f00`

## callees

- `0x180003510`
- `0x180003578`
- `0x1800042ac`
- `0x1800060f4`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180006144`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180006144`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180006168`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180006168`

## pseudocode

```c
char IsXboxLicensingUndocked()
{
  char v0; // bl
  int v2; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180021A4C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180021A4C);
    if ( dword_180021A4C == -1 )
    {
      v2 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v2, 0);
      v0 = 1;
      if ( v2 != 5 && (unsigned int)(v2 - 11) > 1
        || !(unsigned __int8)IsShouldLicenseManagerServiceAutoStopPresent()
        || !(unsigned int)ShouldLicenseManagerServiceAutoStop() )
      {
        v0 = 0;
      }
      byte_180021A50 = v0;
      Init_thread_footer(&dword_180021A4C);
    }
  }
  return byte_180021A50;
}

```

## disassembly

```asm
0x1800060f4  push    rbx
0x1800060f6  sub     rsp, 20h
0x1800060fa  mov     ecx, cs:_tls_index
0x180006100  mov     rax, gs:58h
0x180006109  mov     edx, 4
0x18000610e  mov     rax, [rax+rcx*8]
0x180006112  mov     eax, [rdx+rax]
0x180006115  cmp     cs:dword_180021A4C, eax
0x18000611b  jle     short loc_180006186
0x18000611d  lea     rcx, dword_180021A4C
0x180006124  call    _Init_thread_header
0x180006129  cmp     cs:dword_180021A4C, 0FFFFFFFFh
0x180006130  jnz     short loc_180006186
0x180006132  xor     r8d, r8d
0x180006135  mov     [rsp+28h+arg_0], 0
0x18000613d  lea     rdx, [rsp+28h+arg_0]
0x180006142  xor     ecx, ecx
0x180006144  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000614a  mov     eax, [rsp+28h+arg_0]
0x18000614e  mov     ebx, 1
0x180006153  cmp     eax, 5
0x180006156  jz      short loc_18000615F
0x180006158  add     eax, 0FFFFFFF5h
0x18000615b  cmp     eax, ebx
0x18000615d  ja      short loc_180006172
0x18000615f  call    IsShouldLicenseManagerServiceAutoStopPresent
0x180006164  test    al, al
0x180006166  jz      short loc_180006172
0x180006168  call    cs:__imp_ShouldLicenseManagerServiceAutoStop
0x18000616e  test    eax, eax
0x180006170  jnz     short loc_180006174
0x180006172  xor     bl, bl
0x180006174  lea     rcx, dword_180021A4C
0x18000617b  mov     cs:byte_180021A50, bl
0x180006181  call    _Init_thread_footer
0x180006186  mov     al, cs:byte_180021A50
0x18000618c  add     rsp, 20h
0x180006190  pop     rbx
0x180006191  retn
```
