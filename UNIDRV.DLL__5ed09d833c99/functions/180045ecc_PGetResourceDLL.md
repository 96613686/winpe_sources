# PGetResourceDLL

- ea: `0x180045ecc`
- end: `0x180045fa4`
- name: `PGetResourceDLL`
- size: `216`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800020b4`
- `0x180021c54`

## callees

- `0x1800039ac`
- `0x18003cbf0`
- `0x18003fe9c`
- `0x180045ecc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180045f2d`
- `KERNEL32!SetLastError` at `0x180045f47`
- `KERNEL32!SetLastError` at `0x180045f61`
- `KERNEL32!SetLastError` at `0x180045f7b`
- `KERNEL32!SetLastError` at `0x180045f2d`
- `KERNEL32!SetLastError` at `0x180045f47`
- `KERNEL32!SetLastError` at `0x180045f61`
- `KERNEL32!SetLastError` at `0x180045f7b`

## string_xrefs

- `0x180045f8e`: `PGetResourceDLL`
- `0x180045f87`: `PGetResourceDLL:NULL pUIInfo.`
- `0x180045f39`: `PGetResourceDLL:Resource DLL name is not specified`
- `0x180045f53`: `PGetResourceDLL:NULL resource option.`
- `0x180045f6d`: `PGetResourceDLL:NULL resource Feature.`

## pseudocode

```c
__int64 __fastcall PGetResourceDLL(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // r9
  __int64 v4; // r10
  __int64 v5; // rax
  __int64 v6; // r9

  v1 = 0;
  if ( a1 )
  {
    v2 = PGetIndexedFeature(a1, 0);
    if ( v2 )
    {
      v5 = PGetIndexedOption(v3, (_DWORD *)(v2 + 84LL * *(unsigned __int8 *)(v4 + 2)), *(_BYTE *)(v4 + 3) & 0x7F);
      if ( v5 )
      {
        if ( !*(_DWORD *)(v5 + 12) || (v1 = *(unsigned int *)(v5 + 12) + *(_QWORD *)(v6 + 320)) == 0 )
        {
          SetLastError(0x57u);
          WriteDbgTraceWarning(
            (__int64)"PGetResourceDLL",
            (__int64)L"PGetResourceDLL:Resource DLL name is not specified");
        }
      }
      else
      {
        SetLastError(0x57u);
        WriteDbgTraceWarning((__int64)"PGetResourceDLL", (__int64)L"PGetResourceDLL:NULL resource option.");
      }
    }
    else
    {
      SetLastError(0x57u);
      WriteDbgTraceWarning((__int64)"PGetResourceDLL", (__int64)L"PGetResourceDLL:NULL resource Feature.");
    }
  }
  else
  {
    SetLastError(0x57u);
    WriteDbgTraceWarning((__int64)"PGetResourceDLL", (__int64)L"PGetResourceDLL:NULL pUIInfo.");
  }
  return v1;
}

```

## disassembly

```asm
0x180045ecc  push    rbx
0x180045ece  sub     rsp, 20h
0x180045ed2  xor     ebx, ebx
0x180045ed4  mov     r10, rdx
0x180045ed7  mov     r9, rcx
0x180045eda  test    rcx, rcx
0x180045edd  jz      loc_180045F76
0x180045ee3  xor     edx, edx
0x180045ee5  call    PGetIndexedFeature
0x180045eea  mov     rcx, rax
0x180045eed  test    rax, rax
0x180045ef0  jz      short loc_180045F5C
0x180045ef2  movzx   eax, byte ptr [r10+2]
0x180045ef7  movzx   r8d, byte ptr [r10+3]
0x180045efc  imul    rdx, rax, 54h ; 'T'
0x180045f00  and     r8d, 7Fh
0x180045f04  add     rdx, rcx
0x180045f07  mov     rcx, r9
0x180045f0a  call    PGetIndexedOption
0x180045f0f  test    rax, rax
0x180045f12  jz      short loc_180045F42
0x180045f14  cmp     [rax+0Ch], ebx
0x180045f17  jz      short loc_180045F28
0x180045f19  mov     ecx, [rax+0Ch]
0x180045f1c  mov     rbx, [r9+140h]
0x180045f23  add     rbx, rcx
0x180045f26  jnz     short loc_180045F9A
0x180045f28  mov     ecx, 57h ; 'W'; dwErrCode
0x180045f2d  call    cs:__imp_SetLastError
0x180045f34  nop     dword ptr [rax+rax+00h]
0x180045f39  lea     rdx, aPgetresourcedl_0; "PGetResourceDLL:Resource DLL name is no"...
0x180045f40  jmp     short loc_180045F8E
0x180045f42  mov     ecx, 57h ; 'W'; dwErrCode
0x180045f47  call    cs:__imp_SetLastError
0x180045f4e  nop     dword ptr [rax+rax+00h]
0x180045f53  lea     rdx, aPgetresourcedl_2; "PGetResourceDLL:NULL resource option."
0x180045f5a  jmp     short loc_180045F8E
0x180045f5c  mov     ecx, 57h ; 'W'; dwErrCode
0x180045f61  call    cs:__imp_SetLastError
0x180045f68  nop     dword ptr [rax+rax+00h]
0x180045f6d  lea     rdx, aPgetresourcedl; "PGetResourceDLL:NULL resource Feature."
0x180045f74  jmp     short loc_180045F8E
0x180045f76  mov     ecx, 57h ; 'W'; dwErrCode
0x180045f7b  call    cs:__imp_SetLastError
0x180045f82  nop     dword ptr [rax+rax+00h]
0x180045f87  lea     rdx, aPgetresourcedl_1; "PGetResourceDLL:NULL pUIInfo."
0x180045f8e  lea     rcx, aPgetresourcedl_3; "PGetResourceDLL"
0x180045f95  call    WriteDbgTraceWarning
0x180045f9a  mov     rax, rbx
0x180045f9d  add     rsp, 20h
0x180045fa1  pop     rbx
0x180045fa2  retn
```
