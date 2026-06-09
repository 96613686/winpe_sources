# CleanupJsonValue(JsonValue * *)

- ea: `0x18001a474`
- end: `0x18001a509`
- name: `?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z`
- size: `149`
- prototype: `void __fastcall(struct JsonValue **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001a354`
- `0x18001a510`
- `0x18001faec`
- `0x18001ff90`
- `0x18002043c`

## callees

- `0x18001a3d0`
- `0x18001a474`
- `0x18001a510`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a4bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a4e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a4bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a4e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4f1`

## pseudocode

```c
void __fastcall CleanupJsonValue(struct JsonValue **a1)
{
  _QWORD *v1; // rdx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rdi
  HANDLE v6; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( *(_DWORD *)v1 )
    {
      if ( *(_DWORD *)v1 == 4 )
      {
        CleanupJsonValueList(v1 + 1);
      }
      else if ( *(_DWORD *)v1 == 5 )
      {
        CleanupJsonObject(v1 + 1);
      }
    }
    else
    {
      v3 = (void *)v1[1];
      if ( v3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
        *((_QWORD *)*a1 + 1) = 0;
      }
    }
    v5 = *a1;
    if ( *a1 )
    {
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x18001a474  mov     [rsp+arg_0], rbx
0x18001a479  push    rdi
0x18001a47a  sub     rsp, 20h
0x18001a47e  mov     rdx, [rcx]
0x18001a481  mov     rbx, rcx
0x18001a484  test    rdx, rdx
0x18001a487  jz      short loc_18001A4FE
0x18001a489  mov     r8d, [rdx]
0x18001a48c  test    r8d, r8d
0x18001a48f  jz      short loc_18001A4B3
0x18001a491  sub     r8d, 4
0x18001a495  jz      short loc_18001A4A8
0x18001a497  cmp     r8d, 1
0x18001a49b  jnz     short loc_18001A4DB
0x18001a49d  lea     rcx, [rdx+8]
0x18001a4a1  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x18001a4a6  jmp     short loc_18001A4DB
0x18001a4a8  lea     rcx, [rdx+8]
0x18001a4ac  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x18001a4b1  jmp     short loc_18001A4DB
0x18001a4b3  mov     rdi, [rdx+8]
0x18001a4b7  test    rdi, rdi
0x18001a4ba  jz      short loc_18001A4DB
0x18001a4bc  call    cs:__imp_GetProcessHeap
0x18001a4c2  mov     r8, rdi; lpMem
0x18001a4c5  xor     edx, edx; dwFlags
0x18001a4c7  mov     rcx, rax; hHeap
0x18001a4ca  call    cs:__imp_HeapFree
0x18001a4d0  mov     rax, [rbx]
0x18001a4d3  mov     qword ptr [rax+8], 0
0x18001a4db  mov     rdi, [rbx]
0x18001a4de  test    rdi, rdi
0x18001a4e1  jz      short loc_18001A4FE
0x18001a4e3  call    cs:__imp_GetProcessHeap
0x18001a4e9  mov     r8, rdi; lpMem
0x18001a4ec  xor     edx, edx; dwFlags
0x18001a4ee  mov     rcx, rax; hHeap
0x18001a4f1  call    cs:__imp_HeapFree
0x18001a4f7  mov     qword ptr [rbx], 0
0x18001a4fe  mov     rbx, [rsp+28h+arg_0]
0x18001a503  add     rsp, 20h
0x18001a507  pop     rdi
0x18001a508  retn
```
