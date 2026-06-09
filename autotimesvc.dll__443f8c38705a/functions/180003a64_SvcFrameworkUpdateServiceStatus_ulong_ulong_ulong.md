# SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x180003a64`
- end: `0x180003adc`
- name: `?SvcFrameworkUpdateServiceStatus@@YAXKKK@Z`
- size: `120`
- prototype: `void __fastcall(int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800037ec`
- `0x180003860`
- `0x1800039f0`

## callees

- `0x180003a64`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003ad5`

## pseudocode

```c
void __fastcall SvcFrameworkUpdateServiceStatus(int a1, int a2, int a3)
{
  unsigned int v3; // eax
  unsigned int v4; // eax

  if ( a1 == 4 )
  {
    v3 = DWORD1(xmmword_18001C30C) | 0x400;
  }
  else
  {
    v3 = DWORD1(xmmword_18001C30C) & 0xFFFFFBFF;
    if ( a1 == 2 )
    {
      v4 = DWORD1(xmmword_18001C30C) & 0xFFFFFBFE;
      goto LABEL_4;
    }
  }
  v4 = v3 | 1;
LABEL_4:
  DWORD1(xmmword_18001C30C) = v4;
  LODWORD(xmmword_18001C30C) = a1;
  DWORD2(xmmword_18001C30C) = a2;
  HIDWORD(qword_18001C31C) = a3;
  if ( a1 == 4 || a1 == 1 )
    LODWORD(qword_18001C31C) = 0;
  else
    LODWORD(qword_18001C31C) = dword_18001C1F4++;
  SetServiceStatus((SERVICE_STATUS_HANDLE)qword_18001C328, (LPSERVICE_STATUS)&dword_18001C308);
}

```

## disassembly

```asm
0x180003a64  mov     eax, dword ptr cs:xmmword_18001C30C+4
0x180003a6a  cmp     ecx, 4
0x180003a6d  jnz     short loc_180003AAF
0x180003a6f  bts     eax, 0Ah
0x180003a73  or      eax, 1
0x180003a76  mov     dword ptr cs:xmmword_18001C30C+4, eax
0x180003a7c  mov     dword ptr cs:xmmword_18001C30C, ecx
0x180003a82  mov     dword ptr cs:xmmword_18001C30C+8, edx
0x180003a88  mov     dword ptr cs:qword_18001C31C+4, r8d
0x180003a8f  cmp     ecx, 4
0x180003a92  jz      short loc_180003ABD
0x180003a94  cmp     ecx, 1
0x180003a97  jz      short loc_180003ABD
0x180003a99  mov     eax, cs:dword_18001C1F4
0x180003a9f  mov     dword ptr cs:qword_18001C31C, eax
0x180003aa5  inc     eax
0x180003aa7  mov     cs:dword_18001C1F4, eax
0x180003aad  jmp     short loc_180003AC7
0x180003aaf  btr     eax, 0Ah
0x180003ab3  cmp     ecx, 2
0x180003ab6  jnz     short loc_180003A73
0x180003ab8  and     eax, 0FFFFFFFEh
0x180003abb  jmp     short loc_180003A76
0x180003abd  mov     dword ptr cs:qword_18001C31C, 0
0x180003ac7  mov     rcx, cs:qword_18001C328
0x180003ace  lea     rdx, dword_18001C308
0x180003ad5  jmp     cs:__imp_SetServiceStatus
```
