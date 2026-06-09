# SIPolicyPmUpdateTokenBegin

- ea: `0x180021ffc`
- end: `0x1800220d8`
- name: `SIPolicyPmUpdateTokenBegin`
- size: `220`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180011f20`

## callees

- `0x180020b44`
- `0x180021930`
- `0x180021ffc`
- `0x180022bb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002207e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002207e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180022035`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180022035`
- `ntdll!RtlCreateUnicodeString` at `0x18002209a`
- `ntdll!RtlCreateUnicodeString` at `0x18002209a`
- `ntdll!RtlInitUnicodeString` at `0x18002202f`
- `ntdll!RtlInitUnicodeString` at `0x18002202f`
- `ntdll!RtlFreeUnicodeString` at `0x1800220bb`
- `ntdll!RtlFreeUnicodeString` at `0x1800220bb`

## pseudocode

```c
__int64 __fastcall SIPolicyPmUpdateTokenBegin(PCWSTR SourceString, void *a2, ULONG a3, struct _UNICODE_STRING **a4)
{
  struct _UNICODE_STRING *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  char IsStateSeparationEnabled; // al
  __int64 v12; // rcx
  int v13; // edi
  struct _UNICODE_STRING *v14; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF

  v8 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v10, v9);
  v13 = SIPolicyPmBuildPathFromPolicyID(0, &DestinationString, IsStateSeparationEnabled, 0, 0, &UnicodeString);
  if ( v13 >= 0 )
  {
    v13 = SIPolicyPmWritePolicy(v12, &UnicodeString, a2, a3);
    if ( v13 >= 0 )
    {
      v14 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x28u);
      v8 = v14;
      if ( v14 )
      {
        if ( RtlCreateUnicodeString(v14 + 1, SourceString) )
        {
          v8[2].Length = 257;
          *a4 = v8;
          v8 = 0;
        }
        else
        {
          v13 = -1073741670;
        }
      }
      else
      {
        v13 = -1073741801;
      }
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  SIPolicyPmCloseTransactionHandle(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180021ffc  push    rbx
0x180021ffe  push    rbp
0x180021fff  push    rsi
0x180022000  push    rdi
0x180022001  push    r14
0x180022003  push    r15
0x180022005  sub     rsp, 58h
0x180022009  mov     r15, rdx
0x18002200c  mov     rsi, rcx
0x18002200f  mov     rdx, rcx; SourceString
0x180022012  xorps   xmm0, xmm0
0x180022015  xorps   xmm1, xmm1
0x180022018  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18002201d  mov     r14, r9
0x180022020  mov     ebp, r8d
0x180022023  xor     ebx, ebx
0x180022025  movups  xmmword ptr [rsp+88h+UnicodeString.Length], xmm0
0x18002202a  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x18002202f  call    cs:__imp_RtlInitUnicodeString
0x180022035  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002203b  lea     rcx, [rsp+88h+UnicodeString]
0x180022040  xor     r9d, r9d
0x180022043  mov     [rsp+88h+var_60], rcx
0x180022048  lea     rdx, [rsp+88h+DestinationString]
0x18002204d  xor     ecx, ecx
0x18002204f  mov     [rsp+88h+var_68], rbx
0x180022054  mov     r8b, al
0x180022057  call    SIPolicyPmBuildPathFromPolicyID
0x18002205c  mov     edi, eax
0x18002205e  test    eax, eax
0x180022060  js      short loc_1800220B6
0x180022062  mov     r9d, ebp
0x180022065  lea     rdx, [rsp+88h+UnicodeString]
0x18002206a  mov     r8, r15
0x18002206d  call    SIPolicyPmWritePolicy
0x180022072  mov     edi, eax
0x180022074  test    eax, eax
0x180022076  js      short loc_1800220B6
0x180022078  lea     edx, [rbx+28h]; uBytes
0x18002207b  lea     ecx, [rbx+40h]; uFlags
0x18002207e  call    cs:__imp_LocalAlloc
0x180022084  mov     rbx, rax
0x180022087  test    rax, rax
0x18002208a  jnz     short loc_180022093
0x18002208c  mov     edi, 0C0000017h
0x180022091  jmp     short loc_1800220B6
0x180022093  lea     rcx, [rax+10h]; DestinationString
0x180022097  mov     rdx, rsi; SourceString
0x18002209a  call    cs:__imp_RtlCreateUnicodeString
0x1800220a0  test    al, al
0x1800220a2  jnz     short loc_1800220AB
0x1800220a4  mov     edi, 0C000009Ah
0x1800220a9  jmp     short loc_1800220B6
0x1800220ab  mov     word ptr [rbx+20h], 101h
0x1800220b1  mov     [r14], rbx
0x1800220b4  xor     ebx, ebx
0x1800220b6  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x1800220bb  call    cs:__imp_RtlFreeUnicodeString
0x1800220c1  mov     rcx, rbx; hMem
0x1800220c4  call    SIPolicyPmCloseTransactionHandle
0x1800220c9  mov     eax, edi
0x1800220cb  add     rsp, 58h
0x1800220cf  pop     r15
0x1800220d1  pop     r14
0x1800220d3  pop     rdi
0x1800220d4  pop     rsi
0x1800220d5  pop     rbp
0x1800220d6  pop     rbx
0x1800220d7  retn
```
