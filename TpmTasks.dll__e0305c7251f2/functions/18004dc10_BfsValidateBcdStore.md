# BfsValidateBcdStore

- ea: `0x18004dc10`
- end: `0x18004ddae`
- name: `BfsValidateBcdStore`
- size: `414`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180048c3c`

## callees

- `0x1800078b0`
- `0x18004dc10`
- `0x18004f888`
- `0x180051084`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004dd87`
- `ntdll!RtlNtStatusToDosError` at `0x18004dd87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004dd35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004dd59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004dd35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004dd59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004dd26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004dd4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004dd26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004dd4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dd8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dd8f`
- `bcd!BcdCloseObject` at `0x18004dd68`
- `bcd!BcdCloseObject` at `0x18004dd68`
- `bcd!BcdOpenObject` at `0x18004dc81`
- `bcd!BcdOpenObject` at `0x18004dc81`
- `bcd!BcdCloseStore` at `0x18004dd77`
- `bcd!BcdCloseStore` at `0x18004dd77`
- `bcd!BcdOpenStore` at `0x18004dc62`
- `bcd!BcdOpenStore` at `0x18004dc62`
- `bcd!BcdGetElementData` at `0x18004dcac`
- `bcd!BcdGetElementData` at `0x18004dcac`

## pseudocode

```c
__int64 BfsValidateBcdStore()
{
  void *v0; // rdi
  unsigned int v1; // esi
  NTSTATUS ElementData; // ebx
  unsigned int v3; // r14d
  unsigned int v4; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax
  ULONG v7; // eax
  int v9; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-3Ch] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF

  v0 = 0;
  v9 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  lpMem = 0;
  v14 = 0;
  v1 = 0;
  ElementData = BcdOpenStore(0, 2, &v12);
  if ( ElementData < 0 )
    goto LABEL_17;
  ElementData = BcdOpenObject(v12, &GUID_WINDOWS_BOOTMGR, &v13);
  if ( ElementData < 0 )
    goto LABEL_17;
  v9 = 16;
  v3 = 0;
  ElementData = BcdGetElementData(v13, 587202563, &v14, &v9);
  if ( ElementData >= 0 )
  {
    v3 = BfspValidateBcdEntry(v12, &v14);
    if ( v3 )
      goto LABEL_13;
  }
  ElementData = BfspGetBcdElementData(v13, 603979777, &lpMem, &v10);
  if ( ElementData >= 0 && (v10 & 0xF) == 0 )
  {
    v4 = v10 >> 4;
    v9 = 16;
    if ( v10 >> 4 )
    {
      do
      {
        v3 = BfspValidateBcdEntry(v12, (char *)lpMem + 16 * v1);
        if ( v3 )
          break;
        ++v1;
      }
      while ( v1 < v4 );
    }
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    v0 = 0;
LABEL_13:
    v1 = v3;
    goto LABEL_15;
  }
  v0 = lpMem;
LABEL_15:
  if ( v0 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v0);
  }
LABEL_17:
  if ( v13 )
    BcdCloseObject(v13);
  if ( v12 )
    BcdCloseStore(v12);
  if ( !v1 && ElementData < 0 )
  {
    v7 = RtlNtStatusToDosError(ElementData);
    SetLastError(v7);
  }
  return v1;
}

```

## disassembly

```asm
0x18004dc10  push    rbp
0x18004dc12  push    rbx
0x18004dc13  push    rsi
0x18004dc14  push    rdi
0x18004dc15  push    r14
0x18004dc17  mov     rbp, rsp
0x18004dc1a  sub     rsp, 60h
0x18004dc1e  mov     rax, cs:__security_cookie
0x18004dc25  xor     rax, rsp
0x18004dc28  mov     [rbp+var_10], rax
0x18004dc2c  xor     edi, edi
0x18004dc2e  mov     [rbp+var_40], 0
0x18004dc35  xorps   xmm0, xmm0
0x18004dc38  mov     [rbp+var_3C], 0
0x18004dc3f  lea     r8, [rbp+var_30]
0x18004dc43  mov     [rbp+var_30], 0
0x18004dc4b  xor     ecx, ecx
0x18004dc4d  mov     [rbp+var_28], 0
0x18004dc55  lea     edx, [rdi+2]
0x18004dc58  mov     [rbp+lpMem], rdi
0x18004dc5c  movups  [rbp+var_20], xmm0
0x18004dc60  xor     esi, esi
0x18004dc62  call    cs:__imp_BcdOpenStore
0x18004dc68  mov     ebx, eax
0x18004dc6a  test    eax, eax
0x18004dc6c  js      loc_18004DD5F
0x18004dc72  mov     rcx, [rbp+var_30]
0x18004dc76  lea     r8, [rbp+var_28]
0x18004dc7a  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18004dc81  call    cs:__imp_BcdOpenObject
0x18004dc87  mov     ebx, eax
0x18004dc89  test    eax, eax
0x18004dc8b  js      loc_18004DD5F
0x18004dc91  mov     rcx, [rbp+var_28]
0x18004dc95  lea     r9, [rbp+var_40]
0x18004dc99  lea     r8, [rbp+var_20]
0x18004dc9d  mov     [rbp+var_40], 10h
0x18004dca4  mov     edx, 23000003h
0x18004dca9  xor     r14d, r14d
0x18004dcac  call    cs:__imp_BcdGetElementData
0x18004dcb2  mov     ebx, eax
0x18004dcb4  test    eax, eax
0x18004dcb6  js      short loc_18004DCCC
0x18004dcb8  mov     rcx, [rbp+var_30]
0x18004dcbc  lea     rdx, [rbp+var_20]
0x18004dcc0  call    BfspValidateBcdEntry
0x18004dcc5  mov     r14d, eax
0x18004dcc8  test    eax, eax
0x18004dcca  jnz     short loc_18004DD3D
0x18004dccc  mov     rcx, [rbp+var_28]
0x18004dcd0  lea     r9, [rbp+var_3C]
0x18004dcd4  lea     r8, [rbp+lpMem]
0x18004dcd8  mov     edx, 24000001h
0x18004dcdd  call    BfspGetBcdElementData
0x18004dce2  mov     ebx, eax
0x18004dce4  test    eax, eax
0x18004dce6  js      short loc_18004DD42
0x18004dce8  mov     edi, [rbp+var_3C]
0x18004dceb  test    dil, 0Fh
0x18004dcef  jnz     short loc_18004DD42
0x18004dcf1  shr     edi, 4
0x18004dcf4  mov     [rbp+var_40], 10h
0x18004dcfb  test    edi, edi
0x18004dcfd  jz      short loc_18004DD1F
0x18004dcff  mov     rcx, [rbp+var_30]
0x18004dd03  mov     edx, esi
0x18004dd05  shl     rdx, 4
0x18004dd09  add     rdx, [rbp+lpMem]
0x18004dd0d  call    BfspValidateBcdEntry
0x18004dd12  mov     r14d, eax
0x18004dd15  test    eax, eax
0x18004dd17  jnz     short loc_18004DD1F
0x18004dd19  inc     esi
0x18004dd1b  cmp     esi, edi
0x18004dd1d  jb      short loc_18004DCFF
0x18004dd1f  cmp     [rbp+lpMem], 0
0x18004dd24  jz      short loc_18004DD3B
0x18004dd26  call    cs:__imp_GetProcessHeap
0x18004dd2c  mov     r8, [rbp+lpMem]; lpMem
0x18004dd30  xor     edx, edx; dwFlags
0x18004dd32  mov     rcx, rax; hHeap
0x18004dd35  call    cs:__imp_HeapFree
0x18004dd3b  xor     edi, edi
0x18004dd3d  mov     esi, r14d
0x18004dd40  jmp     short loc_18004DD46
0x18004dd42  mov     rdi, [rbp+lpMem]
0x18004dd46  test    rdi, rdi
0x18004dd49  jz      short loc_18004DD5F
0x18004dd4b  call    cs:__imp_GetProcessHeap
0x18004dd51  mov     r8, rdi; lpMem
0x18004dd54  xor     edx, edx; dwFlags
0x18004dd56  mov     rcx, rax; hHeap
0x18004dd59  call    cs:__imp_HeapFree
0x18004dd5f  mov     rcx, [rbp+var_28]
0x18004dd63  test    rcx, rcx
0x18004dd66  jz      short loc_18004DD6E
0x18004dd68  call    cs:__imp_BcdCloseObject
0x18004dd6e  mov     rcx, [rbp+var_30]
0x18004dd72  test    rcx, rcx
0x18004dd75  jz      short loc_18004DD7D
0x18004dd77  call    cs:__imp_BcdCloseStore
0x18004dd7d  test    esi, esi
0x18004dd7f  jnz     short loc_18004DD95
0x18004dd81  test    ebx, ebx
0x18004dd83  jns     short loc_18004DD95
0x18004dd85  mov     ecx, ebx; Status
0x18004dd87  call    cs:__imp_RtlNtStatusToDosError
0x18004dd8d  mov     ecx, eax; dwErrCode
0x18004dd8f  call    cs:__imp_SetLastError
0x18004dd95  mov     eax, esi
0x18004dd97  mov     rcx, [rbp+var_10]
0x18004dd9b  xor     rcx, rsp; StackCookie
0x18004dd9e  call    __security_check_cookie
0x18004dda3  add     rsp, 60h
0x18004dda7  pop     r14
0x18004dda9  pop     rdi
0x18004ddaa  pop     rsi
0x18004ddab  pop     rbx
0x18004ddac  pop     rbp
0x18004ddad  retn
```
