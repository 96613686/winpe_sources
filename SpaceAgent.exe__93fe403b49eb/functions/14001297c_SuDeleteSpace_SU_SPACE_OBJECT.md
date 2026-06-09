# SuDeleteSpace(_SU_SPACE_OBJECT *)

- ea: `0x14001297c`
- end: `0x140012a86`
- name: `?SuDeleteSpace@@YAHPEAU_SU_SPACE_OBJECT@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct _SU_SPACE_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140016cb0`

## callees

- `0x140004114`
- `0x14000b828`
- `0x14000b934`
- `0x14001163c`
- `0x14001297c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400129b1`
- `KERNEL32!SetLastError` at `0x1400129b1`
- `KERNEL32!GetLastError` at `0x140012a44`
- `KERNEL32!GetLastError` at `0x140012a44`
- `KERNEL32!QueryPerformanceCounter` at `0x14001299d`
- `KERNEL32!QueryPerformanceCounter` at `0x1400129e8`
- `KERNEL32!QueryPerformanceCounter` at `0x14001299d`
- `KERNEL32!QueryPerformanceCounter` at `0x1400129e8`

## string_xrefs

- `0x1400129d8`: `SiDeleteSpace`
- `0x140012a23`: `SuDeleteSpace`
- `0x140012a57`: `SuDeleteSpace`

## pseudocode

```c
__int64 __fastcall SuDeleteSpace(struct _SU_SPACE_OBJECT *a1)
{
  unsigned int v2; // edi
  const char *v3; // rsi
  struct _SP_ID *v4; // rbx
  int v5; // r8d
  int v6; // r9d
  char LastError; // al
  int v8; // r8d
  int v9; // r9d
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-28h] BYREF
  LARGE_INTEGER v12; // [rsp+48h] [rbp-20h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]

  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( (*((_BYTE *)a1 + 2720) & 2) != 0 )
  {
    SetLastError(0x32u);
    v2 = 0;
    v3 = "Clustered space not supported";
    v4 = (struct _SU_SPACE_OBJECT *)((char *)a1 + 40);
  }
  else
  {
    v4 = (struct _SU_SPACE_OBJECT *)((char *)a1 + 40);
    v2 = SiDeleteSpace(v4);
    if ( v2 )
      v3 = 0;
    else
      v3 = "SiDeleteSpace";
  }
  QueryPerformanceCounter(&v12);
  if ( v2 )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjx_EventWriteTransfer(
        (_DWORD)v4 + 16,
        (unsigned int)DeleteSpaceSucceeded,
        v5,
        v6,
        (__int64)"SuDeleteSpace",
        (__int64)v4 + 16,
        1000000 * (v12.QuadPart - PerformanceCount.QuadPart) / v13);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    LastError = GetLastError();
    McTemplateK0zsjsq_EventWriteTransfer(
      (_DWORD)v4 + 16,
      (unsigned int)DeleteSpaceFailed,
      v8,
      v9,
      (__int64)"SuDeleteSpace",
      (__int64)v4 + 16,
      (__int64)v3,
      LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x14001297c  mov     [rsp+arg_0], rbx
0x140012981  mov     [rsp+arg_8], rsi
0x140012986  push    rdi
0x140012987  sub     rsp, 60h
0x14001298b  mov     rbx, rcx
0x14001298e  lea     rcx, [rsp+68h+PerformanceCount]; this
0x140012993  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x140012998  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x14001299d  call    cs:__imp_QueryPerformanceCounter
0x1400129a3  test    byte ptr [rbx+0AA0h], 2
0x1400129aa  jz      short loc_1400129C6
0x1400129ac  mov     ecx, 32h ; '2'; dwErrCode
0x1400129b1  call    cs:__imp_SetLastError
0x1400129b7  xor     edi, edi
0x1400129b9  lea     rsi, aClusteredSpace; "Clustered space not supported"
0x1400129c0  add     rbx, 28h ; '('
0x1400129c4  jmp     short loc_1400129E3
0x1400129c6  add     rbx, 28h ; '('
0x1400129ca  mov     rcx, rbx; lpInBuffer
0x1400129cd  call    ?SiDeleteSpace@@YAHPEAU_SP_ID@@@Z; SiDeleteSpace(_SP_ID *)
0x1400129d2  mov     edi, eax
0x1400129d4  test    eax, eax
0x1400129d6  jnz     short loc_1400129E1
0x1400129d8  lea     rsi, aSideletespace; "SiDeleteSpace"
0x1400129df  jmp     short loc_1400129E3
0x1400129e1  xor     esi, esi
0x1400129e3  lea     rcx, [rsp+68h+var_20]; lpPerformanceCount
0x1400129e8  call    cs:__imp_QueryPerformanceCounter
0x1400129ee  test    edi, edi
0x1400129f0  jz      short loc_140012A3B
0x1400129f2  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x1400129f9  jz      short loc_140012A74
0x1400129fb  mov     rax, qword ptr [rsp+68h+var_20]
0x140012a00  lea     rcx, [rbx+10h]
0x140012a04  sub     rax, qword ptr [rsp+68h+PerformanceCount]
0x140012a09  imul    rax, 0F4240h
0x140012a10  cqo
0x140012a12  idiv    [rsp+68h+var_18]
0x140012a17  lea     rdx, DeleteSpaceSucceeded
0x140012a1e  mov     [rsp+68h+var_38], rax
0x140012a23  lea     rax, aSudeletespace; "SuDeleteSpace"
0x140012a2a  mov     [rsp+68h+var_40], rcx
0x140012a2f  mov     [rsp+68h+var_48], rax
0x140012a34  call    McTemplateK0zsjx_EventWriteTransfer
0x140012a39  jmp     short loc_140012A74
0x140012a3b  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x140012a42  jz      short loc_140012A74
0x140012a44  call    cs:__imp_GetLastError
0x140012a4a  mov     [rsp+68h+var_30], eax
0x140012a4e  lea     rcx, [rbx+10h]
0x140012a52  mov     [rsp+68h+var_38], rsi
0x140012a57  lea     rax, aSudeletespace; "SuDeleteSpace"
0x140012a5e  mov     [rsp+68h+var_40], rcx
0x140012a63  lea     rdx, DeleteSpaceFailed
0x140012a6a  mov     [rsp+68h+var_48], rax
0x140012a6f  call    McTemplateK0zsjsq_EventWriteTransfer
0x140012a74  mov     rbx, [rsp+68h+arg_0]
0x140012a79  mov     eax, edi
0x140012a7b  mov     rsi, [rsp+68h+arg_8]
0x140012a80  add     rsp, 60h
0x140012a84  pop     rdi
0x140012a85  retn
```
