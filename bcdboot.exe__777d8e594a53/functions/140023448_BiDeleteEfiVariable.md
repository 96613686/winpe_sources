# BiDeleteEfiVariable

- ea: `0x140023448`
- end: `0x1400235b4`
- name: `BiDeleteEfiVariable`
- size: `364`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140023824`

## callees

- `0x1400133e4`
- `0x140020678`
- `0x14002166c`
- `0x140021888`
- `0x140023448`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140023508`
- `ntdll!RtlInitUnicodeString` at `0x140023508`

## string_xrefs

- `0x140023571`: `Failed to delete "%ws" variable. Status: %x`

## pseudocode

```c
__int64 __fastcall BiDeleteEfiVariable(PCWSTR SourceString)
{
  NTSTATUS v2; // ebx
  unsigned int v3; // eax
  int v4; // eax
  int v6; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall *v7)(struct _UNICODE_STRING *, _DWORD *, _QWORD, int *, _QWORD); // [rsp+38h] [rbp-48h]
  __int64 (__fastcall *v8)(struct _UNICODE_STRING *, _DWORD *, _QWORD, _QWORD, int); // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v11[4]; // [rsp+60h] [rbp-20h] BYREF

  v11[0] = -1947934879;
  v11[1] = 299013066;
  v11[2] = -536867414;
  v11[3] = -1943338088;
  DestinationString = 0;
  v9 = 0;
  v8 = 0;
  v7 = 0;
  v6 = 0;
  if ( (int)BiLookupNtdllProcedureAddress("ZwQuerySystemEnvironmentValueEx") < 0
    || (int)BiLookupNtdllProcedureAddress("ZwSetSystemEnvironmentValueEx") < 0 )
  {
    return (unsigned int)-1073741637;
  }
  else
  {
    v2 = BiAcquirePrivilege(0x16u, (__int64)&v9);
    if ( v2 >= 0 )
    {
      v6 = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      v3 = v7(&DestinationString, v11, 0, &v6, 0);
      v2 = v3;
      if ( v3 == -1073741789 )
      {
        v4 = v8(&DestinationString, v11, 0, 0, 1);
        v2 = v4;
        if ( v4 < 0 )
          BiLogMessage(4, L"Failed to delete \"%ws\" variable. Status: %x", SourceString, (unsigned int)v4);
      }
      else if ( v3 == -1073741568 )
      {
        v2 = 0;
      }
      else
      {
        BiLogMessage(4, L"Failed to query \"%ws\" variable. Status: %x", SourceString, v3);
      }
      BiReleasePrivilege(&v9);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140023448  mov     [rsp-8+arg_8], rbx
0x14002344d  mov     [rsp-8+arg_10], rdi
0x140023452  push    rbp
0x140023453  mov     rbp, rsp
0x140023456  sub     rsp, 80h
0x14002345d  mov     rax, cs:__security_cookie
0x140023464  xor     rax, rsp
0x140023467  mov     [rbp+var_10], rax
0x14002346b  mov     rdi, rcx
0x14002346e  mov     [rbp+var_20], 8BE4DF61h
0x140023475  xorps   xmm0, xmm0
0x140023478  mov     [rbp+var_1C], 11D293CAh
0x14002347f  lea     rcx, aZwquerysysteme; "ZwQuerySystemEnvironmentValueEx"
0x140023486  mov     [rbp+var_18], 0E0000DAAh
0x14002348d  lea     rdx, [rbp+var_48]
0x140023491  mov     [rbp+var_14], 8C2B0398h
0x140023498  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002349c  mov     [rbp+var_38], 0
0x1400234a4  mov     [rbp+var_40], 0
0x1400234ac  mov     [rbp+var_48], 0
0x1400234b4  mov     [rbp+var_50], 0
0x1400234bb  call    BiLookupNtdllProcedureAddress
0x1400234c0  test    eax, eax
0x1400234c2  jns     short loc_1400234CE
0x1400234c4  mov     ebx, 0C00000BBh
0x1400234c9  jmp     loc_140023591
0x1400234ce  lea     rdx, [rbp+var_40]
0x1400234d2  lea     rcx, aZwsetsystemenv; "ZwSetSystemEnvironmentValueEx"
0x1400234d9  call    BiLookupNtdllProcedureAddress
0x1400234de  test    eax, eax
0x1400234e0  js      short loc_1400234C4
0x1400234e2  lea     rdx, [rbp+var_38]
0x1400234e6  mov     ecx, 16h
0x1400234eb  call    BiAcquirePrivilege
0x1400234f0  mov     ebx, eax
0x1400234f2  test    eax, eax
0x1400234f4  js      loc_140023591
0x1400234fa  mov     rdx, rdi; SourceString
0x1400234fd  mov     [rbp+var_50], 0
0x140023504  lea     rcx, [rbp+DestinationString]; DestinationString
0x140023508  call    cs:__imp_RtlInitUnicodeString
0x14002350e  mov     rax, [rbp+var_48]
0x140023512  lea     r9, [rbp+var_50]
0x140023516  xor     r8d, r8d
0x140023519  mov     [rsp+80h+var_60], 0
0x140023522  lea     rdx, [rbp+var_20]
0x140023526  lea     rcx, [rbp+DestinationString]
0x14002352a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002352f  mov     ebx, eax
0x140023531  cmp     eax, 0C0000023h
0x140023536  jz      short loc_14002354C
0x140023538  cmp     eax, 0C0000100h
0x14002353d  jnz     short loc_140023543
0x14002353f  xor     ebx, ebx
0x140023541  jmp     short loc_140023588
0x140023543  lea     rdx, aFailedToQueryW; "Failed to query \"%ws\" variable. Statu"...
0x14002354a  jmp     short loc_140023578
0x14002354c  mov     rax, [rbp+var_40]
0x140023550  lea     rdx, [rbp+var_20]
0x140023554  xor     r9d, r9d
0x140023557  mov     dword ptr [rsp+80h+var_60], 1
0x14002355f  xor     r8d, r8d
0x140023562  lea     rcx, [rbp+DestinationString]
0x140023566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002356b  mov     ebx, eax
0x14002356d  test    eax, eax
0x14002356f  jns     short loc_140023588
0x140023571  lea     rdx, aFailedToDelete_3; "Failed to delete \"%ws\" variable. Stat"...
0x140023578  mov     r9d, eax
0x14002357b  mov     r8, rdi
0x14002357e  mov     ecx, 4
0x140023583  call    BiLogMessage
0x140023588  lea     rcx, [rbp+var_38]
0x14002358c  call    BiReleasePrivilege
0x140023591  mov     eax, ebx
0x140023593  mov     rcx, [rbp+var_10]
0x140023597  xor     rcx, rsp; StackCookie
0x14002359a  call    __security_check_cookie
0x14002359f  lea     r11, [rsp+80h+var_s0]
0x1400235a7  mov     rbx, [r11+18h]
0x1400235ab  mov     rdi, [r11+20h]
0x1400235af  mov     rsp, r11
0x1400235b2  pop     rbp
0x1400235b3  retn
```
