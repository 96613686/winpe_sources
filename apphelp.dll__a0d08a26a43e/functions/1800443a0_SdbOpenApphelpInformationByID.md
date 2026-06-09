# SdbOpenApphelpInformationByID

- ea: `0x1800443a0`
- end: `0x1800444ee`
- name: `SdbOpenApphelpInformationByID`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003a110`

## callees

- `0x180009720`
- `0x18000f114`
- `0x180018f20`
- `0x180040ac0`
- `0x1800443a0`
- `0x180045f90`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800443e8`
- `ntdll!RtlAllocateHeap` at `0x1800443e8`

## string_xrefs

- `0x180044403`: `SdbOpenApphelpInformationByID`
- `0x1800444bb`: `SdbOpenApphelpInformationByID`
- `0x180044472`: `Error reading database guid for tagref 0x%lx`
- `0x1800444ab`: `Error reading apphelp basic information, apphelp may not be present for 0x%lx`

## pseudocode

```c
_DWORD *__fastcall SdbOpenApphelpInformationByID(__int64 a1, unsigned int a2, int a3)
{
  _DWORD *Heap; // rax
  _DWORD *v8; // rbx
  __int64 v9; // r8
  const char *v10; // r9
  int v11; // ebp
  __int64 v12; // rdx
  __int64 v13; // [rsp+20h] [rbp-28h]
  int v14; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  v14 = 0;
  if ( !a2 )
    return 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xD8u);
  v8 = Heap;
  if ( Heap )
  {
    Heap[7] |= 2u;
    *(_QWORD *)Heap = a1;
    *((_QWORD *)Heap + 1) = 0;
    Heap[6] = a3;
    if ( (unsigned int)SdbTagRefToTagID(a1, a2, &v15, &v14) )
    {
      v11 = v14;
      v12 = v15;
      v8[17] = v14;
      if ( (unsigned int)SdbGetDatabaseGUID(a1, v12, v8 + 8) )
      {
        if ( (unsigned int)SdbpReadApphelpBasicInfo(
                             v15,
                             v11,
                             (int)v8 + 72,
                             (int)v8 + 76,
                             (__int64)(v8 + 20),
                             (__int64)(v8 + 21)) )
          return v8;
        v9 = 2316;
        v10 = "Error reading apphelp basic information, apphelp may not be present for 0x%lx";
      }
      else
      {
        v9 = 2305;
        v10 = "Error reading database guid for tagref 0x%lx";
      }
    }
    else
    {
      v9 = 2298;
      v10 = "Error converting tagref to tagref 0x%lx";
    }
    LODWORD(v13) = a2;
    AslLogCallPrintf(1, "SdbOpenApphelpInformationByID", v9, v10, v13);
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
    return 0;
  }
  AslLogCallPrintf(1, "SdbOpenApphelpInformationByID", 2284, "Error allocating memory for apphelp info context");
  return v8;
}

```

## disassembly

```asm
0x1800443a0  mov     [rsp+arg_0], rbx
0x1800443a5  push    rbp
0x1800443a6  push    rsi
0x1800443a7  push    rdi
0x1800443a8  sub     rsp, 30h
0x1800443ac  mov     [rsp+48h+arg_18], 0
0x1800443b5  mov     ebp, r8d
0x1800443b8  mov     [rsp+48h+arg_8], 0
0x1800443c0  mov     edi, edx
0x1800443c2  mov     rsi, rcx
0x1800443c5  test    edx, edx
0x1800443c7  jnz     short loc_1800443D0
0x1800443c9  xor     eax, eax
0x1800443cb  jmp     loc_1800444E1
0x1800443d0  mov     rcx, gs:60h
0x1800443d9  mov     edx, 8; Flags
0x1800443de  mov     r8d, 0D8h; Size
0x1800443e4  mov     rcx, [rcx+30h]; HeapHandle
0x1800443e8  call    cs:__imp_RtlAllocateHeap
0x1800443ee  mov     rbx, rax
0x1800443f1  test    rax, rax
0x1800443f4  jnz     short loc_180044417
0x1800443f6  lea     r9, aErrorAllocatin_2; "Error allocating memory for apphelp inf"...
0x1800443fd  mov     r8d, 8ECh
0x180044403  lea     rdx, aSdbopenapphelp_5; "SdbOpenApphelpInformationByID"
0x18004440a  lea     ecx, [rax+1]
0x18004440d  call    AslLogCallPrintf
0x180044412  jmp     loc_1800444DE
0x180044417  or      dword ptr [rax+1Ch], 2
0x18004441b  lea     r9, [rsp+48h+arg_8]
0x180044420  lea     r8, [rsp+48h+arg_18]
0x180044425  mov     [rax], rsi
0x180044428  mov     edx, edi
0x18004442a  mov     qword ptr [rax+8], 0
0x180044432  mov     rcx, rsi
0x180044435  mov     [rax+18h], ebp
0x180044438  call    SdbTagRefToTagID
0x18004443d  test    eax, eax
0x18004443f  jnz     short loc_180044450
0x180044441  mov     r8d, 8FAh
0x180044447  lea     r9, aErrorConvertin; "Error converting tagref to tagref 0x%lx"
0x18004444e  jmp     short loc_1800444B2
0x180044450  mov     ebp, [rsp+48h+arg_8]
0x180044454  lea     r8, [rbx+20h]
0x180044458  mov     rdx, [rsp+48h+arg_18]
0x18004445d  mov     rcx, rsi
0x180044460  mov     [rbx+44h], ebp
0x180044463  call    SdbGetDatabaseGUID
0x180044468  test    eax, eax
0x18004446a  jnz     short loc_18004447B
0x18004446c  mov     r8d, 901h
0x180044472  lea     r9, aErrorReadingDa_0; "Error reading database guid for tagref "...
0x180044479  jmp     short loc_1800444B2
0x18004447b  mov     rcx, [rsp+48h+arg_18]
0x180044480  lea     rdx, [rbx+50h]
0x180044484  lea     rax, [rbx+54h]
0x180044488  mov     [rsp+48h+var_20], rax
0x18004448d  lea     r9, [rbx+4Ch]
0x180044491  mov     [rsp+48h+var_28], rdx
0x180044496  lea     r8, [rbx+48h]
0x18004449a  mov     edx, ebp
0x18004449c  call    SdbpReadApphelpBasicInfo
0x1800444a1  test    eax, eax
0x1800444a3  jnz     short loc_1800444DE
0x1800444a5  mov     r8d, 90Ch
0x1800444ab  lea     r9, aErrorReadingAp; "Error reading apphelp basic information"...
0x1800444b2  mov     ecx, 1
0x1800444b7  mov     dword ptr [rsp+48h+var_28], edi
0x1800444bb  lea     rdx, aSdbopenapphelp_5; "SdbOpenApphelpInformationByID"
0x1800444c2  call    AslLogCallPrintf
0x1800444c7  mov     rcx, gs:60h
0x1800444d0  mov     rdx, rbx
0x1800444d3  mov     rcx, [rcx+30h]
0x1800444d7  call    AslFree
0x1800444dc  xor     ebx, ebx
0x1800444de  mov     rax, rbx
0x1800444e1  mov     rbx, [rsp+48h+arg_0]
0x1800444e6  add     rsp, 30h
0x1800444ea  pop     rdi
0x1800444eb  pop     rsi
0x1800444ec  pop     rbp
0x1800444ed  retn
```
