# PGetResourceDLL

- ea: `0x180044bfc`
- end: `0x180044cbb`
- name: `PGetResourceDLL`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000225c`
- `0x18002176c`

## callees

- `0x1800039d8`
- `0x18003c6e0`
- `0x18003ed80`
- `0x180044bfc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180044c5d`
- `KERNEL32!SetLastError` at `0x180044c71`
- `KERNEL32!SetLastError` at `0x180044c85`
- `KERNEL32!SetLastError` at `0x180044c99`
- `KERNEL32!SetLastError` at `0x180044c5d`
- `KERNEL32!SetLastError` at `0x180044c71`
- `KERNEL32!SetLastError` at `0x180044c85`
- `KERNEL32!SetLastError` at `0x180044c99`

## string_xrefs

- `0x180044ca6`: `PGetResourceDLL`
- `0x180044c9f`: `PGetResourceDLL:NULL pUIInfo.`
- `0x180044c63`: `PGetResourceDLL:Resource DLL name is not specified`
- `0x180044c77`: `PGetResourceDLL:NULL resource option.`
- `0x180044c8b`: `PGetResourceDLL:NULL resource Feature.`

## pseudocode

```c
__int64 __fastcall PGetResourceDLL(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // r9
  __int64 v6; // r10
  __int64 v7; // rax
  __int64 v8; // r9

  v3 = 0;
  if ( a1 )
  {
    v4 = PGetIndexedFeature(a1, 0, a3, a1);
    if ( v4 )
    {
      v7 = PGetIndexedOption(v5, v4 + 84LL * *(unsigned __int8 *)(v6 + 2), *(_BYTE *)(v6 + 3) & 0x7F, v5);
      if ( v7 )
      {
        if ( !*(_DWORD *)(v7 + 12) || (v3 = *(unsigned int *)(v7 + 12) + *(_QWORD *)(v8 + 320)) == 0 )
        {
          SetLastError(0x57u);
          WriteDbgTraceWarning("PGetResourceDLL", L"PGetResourceDLL:Resource DLL name is not specified");
        }
      }
      else
      {
        SetLastError(0x57u);
        WriteDbgTraceWarning("PGetResourceDLL", L"PGetResourceDLL:NULL resource option.");
      }
    }
    else
    {
      SetLastError(0x57u);
      WriteDbgTraceWarning("PGetResourceDLL", L"PGetResourceDLL:NULL resource Feature.");
    }
  }
  else
  {
    SetLastError(0x57u);
    WriteDbgTraceWarning("PGetResourceDLL", L"PGetResourceDLL:NULL pUIInfo.");
  }
  return v3;
}

```

## disassembly

```asm
0x180044bfc  push    rbx
0x180044bfe  sub     rsp, 20h
0x180044c02  xor     ebx, ebx
0x180044c04  mov     r10, rdx
0x180044c07  mov     r9, rcx
0x180044c0a  test    rcx, rcx
0x180044c0d  jz      loc_180044C94
0x180044c13  xor     edx, edx
0x180044c15  call    PGetIndexedFeature
0x180044c1a  mov     rcx, rax
0x180044c1d  test    rax, rax
0x180044c20  jz      short loc_180044C80
0x180044c22  movzx   eax, byte ptr [r10+2]
0x180044c27  movzx   r8d, byte ptr [r10+3]
0x180044c2c  imul    rdx, rax, 54h ; 'T'
0x180044c30  and     r8d, 7Fh
0x180044c34  add     rdx, rcx
0x180044c37  mov     rcx, r9
0x180044c3a  call    PGetIndexedOption
0x180044c3f  test    rax, rax
0x180044c42  jz      short loc_180044C6C
0x180044c44  cmp     [rax+0Ch], ebx
0x180044c47  jz      short loc_180044C58
0x180044c49  mov     ecx, [rax+0Ch]
0x180044c4c  mov     rbx, [r9+140h]
0x180044c53  add     rbx, rcx
0x180044c56  jnz     short loc_180044CB2
0x180044c58  mov     ecx, 57h ; 'W'; dwErrCode
0x180044c5d  call    cs:__imp_SetLastError
0x180044c63  lea     rdx, aPgetresourcedl_0; "PGetResourceDLL:Resource DLL name is no"...
0x180044c6a  jmp     short loc_180044CA6
0x180044c6c  mov     ecx, 57h ; 'W'; dwErrCode
0x180044c71  call    cs:__imp_SetLastError
0x180044c77  lea     rdx, aPgetresourcedl_2; "PGetResourceDLL:NULL resource option."
0x180044c7e  jmp     short loc_180044CA6
0x180044c80  mov     ecx, 57h ; 'W'; dwErrCode
0x180044c85  call    cs:__imp_SetLastError
0x180044c8b  lea     rdx, aPgetresourcedl; "PGetResourceDLL:NULL resource Feature."
0x180044c92  jmp     short loc_180044CA6
0x180044c94  mov     ecx, 57h ; 'W'; dwErrCode
0x180044c99  call    cs:__imp_SetLastError
0x180044c9f  lea     rdx, aPgetresourcedl_1; "PGetResourceDLL:NULL pUIInfo."
0x180044ca6  lea     rcx, aPgetresourcedl_3; "PGetResourceDLL"
0x180044cad  call    WriteDbgTraceWarning
0x180044cb2  mov     rax, rbx
0x180044cb5  add     rsp, 20h
0x180044cb9  pop     rbx
0x180044cba  retn
```
