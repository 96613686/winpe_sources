# ExprBooleanAND::InsertAsORChild(ExprBooleanOR &,StoragePool &)

- ea: `0x1800018e0`
- end: `0x180001a6c`
- name: `?InsertAsORChild@ExprBooleanAND@@UEAAXAEAVExprBooleanOR@@AEAVStoragePool@@@Z`
- size: `396`
- prototype: `void(ExprBooleanAND *__hidden this, struct ExprBooleanOR *, struct StoragePool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800018e0`
- `0x180001c14`
- `0x180003d54`

## import_xrefs

- `msvcrt!malloc` at `0x1800019b5`
- `msvcrt!malloc` at `0x1800019b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001997`

## string_xrefs

- `0x180001a10`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180001a4e`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
void __fastcall ExprBooleanAND::InsertAsORChild(ExprBooleanAND *this, struct ExprBooleanOR *a2, struct StoragePool *a3)
{
  __int64 v4; // rdx
  int v6; // edi
  unsigned __int64 v8; // rax
  __int64 v9; // rax
  struct ExprConstant *v10; // r8
  __int64 v11; // rcx
  size_t v12; // r12
  _QWORD *v13; // r15
  __int64 v14; // rbx
  void *v15; // rax
  unsigned __int64 v16; // rax
  unsigned int v17; // edx

  v4 = *((_QWORD *)a3 + 1);
  v6 = 1;
  v8 = *(_QWORD *)(v4 + 16);
  if ( v8 >= 0x18 )
  {
    *(_QWORD *)(v4 + 16) = v8 - 24;
    v9 = *(_QWORD *)(v4 + 8);
    *(_QWORD *)(v4 + 8) = v9 + 24;
    if ( v9 )
      goto LABEL_3;
  }
  v12 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 < 0x18u )
    v12 = 48;
  v13 = CoTaskMemAlloc(0x20u);
  if ( !v13 )
  {
    v13 = 0;
    v17 = 94;
LABEL_17:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v17, 0xC0001204, 0x10u);
    goto LABEL_12;
  }
  v14 = *((_QWORD *)a3 + 1);
  v15 = malloc(v12);
  v13[3] = v14;
  *v13 = v15;
  v13[1] = v15;
  v13[2] = v12;
  if ( !v15 )
  {
    v17 = 34;
    goto LABEL_17;
  }
LABEL_12:
  *(_QWORD *)a3 = v12;
  *((_QWORD *)a3 + 1) = v13;
  v16 = v13[2];
  if ( v16 >= 0x18 )
  {
    v13[2] = v16 - 24;
    v9 = v13[1];
    v13[1] = v9 + 24;
    if ( v9 )
    {
LABEL_3:
      *(_QWORD *)v9 = this;
      *(_DWORD *)(v9 + 8) = 1;
      *(_QWORD *)(v9 + 16) = 0;
      goto LABEL_4;
    }
  }
  InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
  v9 = 0;
LABEL_4:
  v10 = (struct ExprConstant *)*((_QWORD *)this + 3);
  if ( v10 )
  {
    ExprBooleanOR::InsertChild(a2, (struct ExprBooleanOR::Element *)v9, v10);
  }
  else
  {
    *(_QWORD *)(v9 + 16) = *((_QWORD *)a2 + 1);
    v11 = *((_QWORD *)a2 + 1);
    if ( v11 )
      v6 = *(_DWORD *)(v11 + 8) + 1;
    *(_DWORD *)(v9 + 8) = v6;
    *((_QWORD *)a2 + 1) = v9;
    *((_BYTE *)a2 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800018e0  push    rsi
0x1800018e2  push    rdi
0x1800018e3  sub     rsp, 28h
0x1800018e7  mov     [rsp+38h+arg_8], rbp
0x1800018ec  mov     rsi, rdx
0x1800018ef  mov     rdx, [r8+8]
0x1800018f3  mov     rbp, rcx
0x1800018f6  mov     [rsp+38h+arg_18], r14
0x1800018fb  mov     edi, 1
0x180001900  mov     [rsp+38h+var_18], r15
0x180001905  mov     r14, r8
0x180001908  mov     rax, [rdx+10h]
0x18000190c  cmp     rax, 18h
0x180001910  jb      short loc_18000197D
0x180001912  add     rax, 0FFFFFFFFFFFFFFE8h
0x180001916  mov     [rdx+10h], rax
0x18000191a  mov     rax, [rdx+8]
0x18000191e  lea     rcx, [rax+18h]
0x180001922  mov     [rdx+8], rcx
0x180001926  test    rax, rax
0x180001929  jz      short loc_18000197D
0x18000192b  mov     [rax], rbp
0x18000192e  mov     [rax+8], edi
0x180001931  mov     qword ptr [rax+10h], 0
0x180001939  mov     r8, [rbp+18h]; struct ExprConstant *
0x18000193d  mov     r15, [rsp+38h+var_18]
0x180001942  mov     r14, [rsp+38h+arg_18]
0x180001947  mov     rbp, [rsp+38h+arg_8]
0x18000194c  test    r8, r8
0x18000194f  jnz     loc_180001A2F
0x180001955  mov     rcx, [rsi+8]
0x180001959  mov     [rax+10h], rcx
0x18000195d  mov     rcx, [rsi+8]
0x180001961  test    rcx, rcx
0x180001964  jz      short loc_18000196B
0x180001966  mov     edi, [rcx+8]
0x180001969  inc     edi
0x18000196b  mov     [rax+8], edi
0x18000196e  mov     [rsi+8], rax
0x180001972  mov     byte ptr [rsi+10h], 0
0x180001976  add     rsp, 28h
0x18000197a  pop     rdi
0x18000197b  pop     rsi
0x18000197c  retn
0x18000197d  mov     [rsp+38h+arg_10], r12
0x180001982  mov     eax, 30h ; '0'
0x180001987  mov     r12, [r8]
0x18000198a  mov     ecx, 20h ; ' '; cb
0x18000198f  cmp     r12, 18h
0x180001993  cmovb   r12, rax
0x180001997  call    cs:__imp_CoTaskMemAlloc
0x18000199d  mov     r15, rax
0x1800019a0  test    rax, rax
0x1800019a3  jz      loc_180001A40
0x1800019a9  mov     [rsp+38h+arg_0], rbx
0x1800019ae  mov     rcx, r12; Size
0x1800019b1  mov     rbx, [r14+8]
0x1800019b5  call    cs:__imp_malloc
0x1800019bb  mov     [r15+18h], rbx
0x1800019bf  mov     rbx, [rsp+38h+arg_0]
0x1800019c4  mov     [r15], rax
0x1800019c7  mov     [r15+8], rax
0x1800019cb  mov     [r15+10h], r12
0x1800019cf  test    rax, rax
0x1800019d2  jz      loc_180001A65
0x1800019d8  mov     [r14], r12
0x1800019db  mov     r12, [rsp+38h+arg_10]
0x1800019e0  mov     [r14+8], r15
0x1800019e4  mov     rax, [r15+10h]
0x1800019e8  cmp     rax, 18h
0x1800019ec  jb      short loc_180001A0B
0x1800019ee  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800019f2  mov     [r15+10h], rax
0x1800019f6  mov     rax, [r15+8]
0x1800019fa  lea     rcx, [rax+18h]
0x1800019fe  mov     [r15+8], rcx
0x180001a02  test    rax, rax
0x180001a05  jnz     loc_18000192B
0x180001a0b  mov     edx, 64h ; 'd'; unsigned int
0x180001a10  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180001a17  mov     r9d, 10h; unsigned __int16
0x180001a1d  mov     r8d, 0C0001204h; unsigned int
0x180001a23  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180001a28  xor     eax, eax
0x180001a2a  jmp     loc_180001939
0x180001a2f  mov     rdx, rax; struct ExprBooleanOR::Element *
0x180001a32  mov     rcx, rsi; this
0x180001a35  add     rsp, 28h
0x180001a39  pop     rdi
0x180001a3a  pop     rsi
0x180001a3b  jmp     ?InsertChild@ExprBooleanOR@@AEAAXPEAUElement@1@AEAVExprConstant@@@Z; ExprBooleanOR::InsertChild(ExprBooleanOR::Element *,ExprConstant &)
0x180001a40  xor     r15d, r15d
0x180001a43  mov     edx, 5Eh ; '^'; unsigned int
0x180001a48  mov     r9d, 10h; unsigned __int16
0x180001a4e  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180001a55  mov     r8d, 0C0001204h; unsigned int
0x180001a5b  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180001a60  jmp     loc_1800019D8
0x180001a65  mov     edx, 22h ; '"'
0x180001a6a  jmp     short loc_180001A48
```
