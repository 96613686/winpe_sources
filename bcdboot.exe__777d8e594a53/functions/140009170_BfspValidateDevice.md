# BfspValidateDevice

- ea: `0x140009170`
- end: `0x140009520`
- name: `BfspValidateDevice`
- size: `944`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140008400`
- `0x140009170`
- `0x140009528`

## callees

- `0x1400065a0`
- `0x140006a14`
- `0x140008694`
- `0x140009170`
- `0x140009528`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x140018890`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400094f6`
- `KERNEL32!HeapFree` at `0x1400094f6`
- `KERNEL32!HeapAlloc` at `0x1400093ea`
- `KERNEL32!HeapAlloc` at `0x1400093ea`
- `KERNEL32!GetProcessHeap` at `0x1400093d9`
- `KERNEL32!GetProcessHeap` at `0x1400094e8`
- `KERNEL32!GetProcessHeap` at `0x1400093d9`
- `KERNEL32!GetProcessHeap` at `0x1400094e8`

## string_xrefs

- `0x1400094a1`: `Moving to Partition node with path %ws`
- `0x14000944a`: `Moving to File/Ramdisk node with path %ws`
- `0x1400092a7`: `Moving to Composite node`
- `0x140009317`: `Done validating Composite`

## pseudocode

```c
__int64 __fastcall BfspValidateDevice(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v5; // rsi
  _QWORD *v6; // rbx
  __int64 v7; // rax
  int ElementDataWithFlags; // edi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  const wchar_t *v16; // rdx
  int v17; // eax
  int BcdElementData; // eax
  __int64 v19; // r8
  bool v20; // zf
  int v21; // r15d
  void *v22; // rbx
  unsigned int v23; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v25; // r8
  HANDLE v26; // rax
  HANDLE Handle; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v29[2]; // [rsp+38h] [rbp-10h] BYREF
  SIZE_T dwBytes; // [rsp+A0h] [rbp+58h] BYREF

  v5 = a5;
  v6 = (_QWORD *)(a3 + 4);
  v7 = *(_QWORD *)(a3 + 4);
  LODWORD(dwBytes) = 0;
  Handle = 0;
  v29[0] = 0;
  if ( v7 || *(_QWORD *)(a3 + 12) )
  {
    ElementDataWithFlags = BfspValidateDeviceOptions(a1, v6, a5);
    if ( ElementDataWithFlags >= 0 && !*v5 )
      goto LABEL_50;
  }
  else
  {
    ElementDataWithFlags = 0;
  }
  switch ( *(_DWORD *)a3 )
  {
    case 2:
      BfspLogMessage(2, L"Moving to Partition node with path %ws", a3 + 20);
      ElementDataWithFlags = BfspFileExistsOnNtDevice(a4, (const wchar_t *)(a3 + 20), v5);
      BfspLogMessage(2, L"Done validating partition %ws", a3 + 20);
LABEL_45:
      if ( Handle )
        BcdCloseObject(Handle);
      break;
    case 3:
    case 4:
      BfspLogMessage(2, L"Moving to File/Ramdisk node with path %ws", a3 + 24);
      if ( *(_DWORD *)(a3 + 20) )
      {
        ElementDataWithFlags = BfspValidateDevice(a1, a2, (int)a3 + *(_DWORD *)(a3 + 20), (int)a3 + 24, (__int64)v5);
        BfspLogMessage(2, L"Done validating partition/ramdisk %ws", a3 + 24);
      }
      else
      {
        *v5 = 0;
      }
      goto LABEL_50;
    case 5:
      *v5 = 0;
      goto LABEL_50;
    case 8:
      BfspLogMessage(2, L"Moving to Locate node");
      if ( *(_DWORD *)(a3 + 24) )
      {
        BfspLogMessage(2, L"Locate node has parent - moving to parent");
        ElementDataWithFlags = BfspValidateDevice(a1, a2, (int)a3 + *(_DWORD *)(a3 + 24), a4, (__int64)v5);
        goto LABEL_50;
      }
      BfspLogMessage(2, L"Locate Node does not have parent");
      v20 = *(_DWORD *)(a3 + 20) == 1;
      v21 = 0;
      LODWORD(dwBytes) = 0;
      if ( v20 )
      {
        v22 = (void *)(a3 + 32);
        goto LABEL_38;
      }
      v22 = 0;
      if ( !*(_DWORD *)(a3 + 20) )
      {
        ElementDataWithFlags = BcdGetElementDataWithFlags(a2, *(_DWORD *)(a3 + 28), v19, 0, &dwBytes);
        if ( ElementDataWithFlags != -1073741789 )
        {
LABEL_33:
          *v5 = 0;
          goto LABEL_50;
        }
        v23 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v22 = HeapAlloc(ProcessHeap, 8u, v23);
        if ( !v22 )
        {
          ElementDataWithFlags = -1073741801;
          goto LABEL_33;
        }
        ElementDataWithFlags = BcdGetElementDataWithFlags(a2, *(_DWORD *)(a3 + 28), v25, (__int64)v22, &dwBytes);
        if ( ElementDataWithFlags < 0 )
          goto LABEL_33;
        v21 = dwBytes;
      }
LABEL_38:
      ElementDataWithFlags = BfspScanAllDrivesForPath((__int64)v22, v5);
      if ( !v21 )
        goto LABEL_50;
      goto LABEL_48;
    case 0xA:
      BfspLogMessage(2, L"Moving to Composite node");
      v17 = BcdOpenObject(a1, v6, &Handle);
      ElementDataWithFlags = v17;
      if ( v17 != -1073741275 && v17 != -1073741772 )
      {
        if ( v17 < 0 )
          goto LABEL_45;
        BcdElementData = BfspGetBcdElementData((__int64)Handle, 0x3100000Eu, v29, &dwBytes);
        ElementDataWithFlags = BcdElementData;
        if ( BcdElementData != -1073741275 )
        {
          if ( BcdElementData < 0 )
            goto LABEL_45;
          v15 = BfspValidateDevice(a1, a2, v29[0], a4, (__int64)v5);
          v16 = L"Done validating Composite";
          goto LABEL_25;
        }
      }
      goto LABEL_26;
    case 0xB:
      BfspLogMessage(2, L"Moving to Cimfs node");
      v13 = BcdOpenObject(a1, v6, &Handle);
      ElementDataWithFlags = v13;
      if ( v13 != -1073741275 && v13 != -1073741772 )
      {
        if ( v13 < 0 )
          goto LABEL_45;
        v14 = BfspGetBcdElementData((__int64)Handle, 0x31000012u, v29, &dwBytes);
        ElementDataWithFlags = v14;
        if ( v14 != -1073741275 )
        {
          if ( v14 < 0 )
            goto LABEL_45;
          v15 = BfspValidateDevice(a1, a2, v29[0], a4, (__int64)v5);
          v16 = L"Done validating Cimfs";
LABEL_25:
          ElementDataWithFlags = v15;
          BfspLogMessage(2, v16);
          goto LABEL_45;
        }
      }
LABEL_26:
      *v5 = 0;
      ElementDataWithFlags = 0;
      goto LABEL_45;
  }
  v22 = (void *)v29[0];
LABEL_48:
  if ( v22 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v22);
  }
LABEL_50:
  BfspLogMessage(2, L"Returning from device validation");
  return (unsigned int)ElementDataWithFlags;
}

```

## disassembly

```asm
0x140009170  push    rbp
0x140009172  push    rbx
0x140009173  push    rsi
0x140009174  push    rdi
0x140009175  push    r12
0x140009177  push    r13
0x140009179  push    r14
0x14000917b  push    r15
0x14000917d  mov     rbp, rsp
0x140009180  sub     rsp, 48h
0x140009184  mov     rsi, [rbp+arg_20]
0x140009188  lea     rbx, [r8+4]
0x14000918c  mov     rax, [rbx]
0x14000918f  mov     r12, rdx
0x140009192  xor     edx, edx
0x140009194  mov     r13, r9
0x140009197  cmp     rax, qword ptr cs:xmmword_140029910
0x14000919e  mov     r14, r8
0x1400091a1  mov     r15, rcx
0x1400091a4  mov     dword ptr [rbp+dwBytes], edx
0x1400091a7  mov     [rbp+Handle], rdx
0x1400091ab  mov     [rbp+var_10], rdx
0x1400091af  jnz     short loc_1400091C2
0x1400091b1  mov     rax, [rbx+8]
0x1400091b5  cmp     rax, qword ptr cs:xmmword_140029910+8
0x1400091bc  jnz     short loc_1400091C2
0x1400091be  mov     edi, edx
0x1400091c0  jmp     short loc_1400091DD
0x1400091c2  mov     r8, rsi
0x1400091c5  mov     rdx, rbx
0x1400091c8  call    BfspValidateDeviceOptions
0x1400091cd  xor     edx, edx
0x1400091cf  mov     edi, eax
0x1400091d1  test    eax, eax
0x1400091d3  js      short loc_1400091DD
0x1400091d5  cmp     [rsi], edx
0x1400091d7  jz      loc_1400094FC
0x1400091dd  mov     eax, [r14]
0x1400091e0  mov     ecx, 2
0x1400091e5  sub     eax, ecx
0x1400091e7  jz      loc_14000949A
0x1400091ed  sub     eax, 1
0x1400091f0  jz      loc_140009443
0x1400091f6  sub     eax, 1
0x1400091f9  jz      loc_140009443
0x1400091ff  sub     eax, 1
0x140009202  jz      loc_14000943C
0x140009208  sub     eax, 3
0x14000920b  jz      loc_14000933C
0x140009211  sub     eax, ecx
0x140009213  jz      loc_1400092A7
0x140009219  cmp     eax, 1
0x14000921c  jnz     loc_1400094DF
0x140009222  lea     rdx, aMovingToCimfsN; "Moving to Cimfs node"
0x140009229  call    BfspLogMessage
0x14000922e  lea     r8, [rbp+Handle]
0x140009232  mov     rdx, rbx
0x140009235  mov     rcx, r15
0x140009238  call    BcdOpenObject
0x14000923d  mov     ebx, 0C0000225h
0x140009242  mov     edi, eax
0x140009244  cmp     eax, ebx
0x140009246  jz      loc_14000932F
0x14000924c  cmp     eax, 0C0000034h
0x140009251  jz      loc_14000932F
0x140009257  test    eax, eax
0x140009259  js      loc_1400094D1
0x14000925f  mov     rcx, [rbp+Handle]
0x140009263  lea     r9, [rbp+dwBytes]
0x140009267  lea     r8, [rbp+var_10]
0x14000926b  mov     edx, 31000012h
0x140009270  call    BfspGetBcdElementData
0x140009275  mov     edi, eax
0x140009277  cmp     eax, ebx
0x140009279  jz      loc_14000932F
0x14000927f  test    eax, eax
0x140009281  js      loc_1400094D1
0x140009287  mov     r8, [rbp+var_10]
0x14000928b  mov     r9, r13
0x14000928e  mov     rdx, r12
0x140009291  mov     [rsp+48h+var_28], rsi
0x140009296  mov     rcx, r15
0x140009299  call    BfspValidateDevice
0x14000929e  lea     rdx, aDoneValidating_3; "Done validating Cimfs"
0x1400092a5  jmp     short loc_14000931E
0x1400092a7  lea     rdx, aMovingToCompos; "Moving to Composite node"
0x1400092ae  call    BfspLogMessage
0x1400092b3  lea     r8, [rbp+Handle]
0x1400092b7  mov     rdx, rbx
0x1400092ba  mov     rcx, r15
0x1400092bd  call    BcdOpenObject
0x1400092c2  mov     ebx, 0C0000225h
0x1400092c7  mov     edi, eax
0x1400092c9  cmp     eax, ebx
0x1400092cb  jz      short loc_14000932F
0x1400092cd  cmp     eax, 0C0000034h
0x1400092d2  jz      short loc_14000932F
0x1400092d4  test    eax, eax
0x1400092d6  js      loc_1400094D1
0x1400092dc  mov     rcx, [rbp+Handle]
0x1400092e0  lea     r9, [rbp+dwBytes]
0x1400092e4  lea     r8, [rbp+var_10]
0x1400092e8  mov     edx, 3100000Eh
0x1400092ed  call    BfspGetBcdElementData
0x1400092f2  mov     edi, eax
0x1400092f4  cmp     eax, ebx
0x1400092f6  jz      short loc_14000932F
0x1400092f8  test    eax, eax
0x1400092fa  js      loc_1400094D1
0x140009300  mov     r8, [rbp+var_10]
0x140009304  mov     r9, r13
0x140009307  mov     rdx, r12
0x14000930a  mov     [rsp+48h+var_28], rsi
0x14000930f  mov     rcx, r15
0x140009312  call    BfspValidateDevice
0x140009317  lea     rdx, aDoneValidating_0; "Done validating Composite"
0x14000931e  mov     ecx, 2
0x140009323  mov     edi, eax
0x140009325  call    BfspLogMessage
0x14000932a  jmp     loc_1400094D1
0x14000932f  mov     dword ptr [rsi], 0
0x140009335  xor     edi, edi
0x140009337  jmp     loc_1400094D1
0x14000933c  lea     rdx, aMovingToLocate; "Moving to Locate node"
0x140009343  call    BfspLogMessage
0x140009348  cmp     dword ptr [r14+18h], 0
0x14000934d  mov     ecx, 2
0x140009352  jz      short loc_140009381
0x140009354  lea     rdx, aLocateNodeHasP; "Locate node has parent - moving to pare"...
0x14000935b  call    BfspLogMessage
0x140009360  mov     r8d, [r14+18h]
0x140009364  mov     r9, r13
0x140009367  add     r8, r14
0x14000936a  mov     [rsp+48h+var_28], rsi
0x14000936f  mov     rdx, r12
0x140009372  mov     rcx, r15
0x140009375  call    BfspValidateDevice
0x14000937a  mov     edi, eax
0x14000937c  jmp     loc_1400094FC
0x140009381  lea     rdx, aLocateNodeDoes; "Locate Node does not have parent"
0x140009388  call    BfspLogMessage
0x14000938d  xor     r13d, r13d
0x140009390  cmp     dword ptr [r14+14h], 1
0x140009395  mov     r15d, r13d
0x140009398  mov     dword ptr [rbp+dwBytes], r13d
0x14000939c  jnz     short loc_1400093A4
0x14000939e  lea     rbx, [r14+20h]
0x1400093a2  jmp     short loc_140009421
0x1400093a4  mov     rbx, r13
0x1400093a7  cmp     [r14+14h], r13d
0x1400093ab  jnz     short loc_140009421
0x1400093ad  mov     edx, [r14+1Ch]
0x1400093b1  lea     rax, [rbp+dwBytes]
0x1400093b5  xor     r9d, r9d
0x1400093b8  mov     [rsp+48h+var_28], rax
0x1400093bd  mov     rcx, r12
0x1400093c0  call    BcdGetElementDataWithFlags
0x1400093c5  mov     edi, eax
0x1400093c7  cmp     eax, 0C0000023h
0x1400093cc  jz      short loc_1400093D6
0x1400093ce  mov     [rsi], r13d
0x1400093d1  jmp     loc_1400094FC
0x1400093d6  mov     ebx, dword ptr [rbp+dwBytes]
0x1400093d9  call    cs:__imp_GetProcessHeap
0x1400093df  mov     r8d, ebx; dwBytes
0x1400093e2  mov     edx, 8; dwFlags
0x1400093e7  mov     rcx, rax; hHeap
0x1400093ea  call    cs:__imp_HeapAlloc
0x1400093f0  mov     rbx, rax
0x1400093f3  test    rax, rax
0x1400093f6  jnz     short loc_1400093FF
0x1400093f8  mov     edi, 0C0000017h
0x1400093fd  jmp     short loc_1400093CE
0x1400093ff  mov     edx, [r14+1Ch]
0x140009403  lea     rax, [rbp+dwBytes]
0x140009407  mov     r9, rbx
0x14000940a  mov     [rsp+48h+var_28], rax
0x14000940f  mov     rcx, r12
0x140009412  call    BcdGetElementDataWithFlags
0x140009417  mov     edi, eax
0x140009419  test    eax, eax
0x14000941b  js      short loc_1400093CE
0x14000941d  mov     r15d, dword ptr [rbp+dwBytes]
0x140009421  mov     rdx, rsi
0x140009424  mov     rcx, rbx
0x140009427  call    BfspScanAllDrivesForPath
0x14000942c  mov     edi, eax
0x14000942e  test    r15d, r15d
0x140009431  jz      loc_1400094FC
0x140009437  jmp     loc_1400094E3
0x14000943c  mov     [rsi], edx
0x14000943e  jmp     loc_1400094FC
0x140009443  lea     rbx, [r14+18h]
0x140009447  mov     r8, rbx
0x14000944a  lea     rdx, aMovingToFileRa; "Moving to File/Ramdisk node with path %"...
0x140009451  call    BfspLogMessage
0x140009456  cmp     dword ptr [r14+14h], 0
0x14000945b  jnz     short loc_140009468
0x14000945d  mov     dword ptr [rsi], 0
0x140009463  jmp     loc_1400094FC
0x140009468  mov     r8d, [r14+14h]
0x14000946c  mov     r9, rbx
0x14000946f  add     r8, r14
0x140009472  mov     [rsp+48h+var_28], rsi
0x140009477  mov     rdx, r12
0x14000947a  mov     rcx, r15
0x14000947d  call    BfspValidateDevice
0x140009482  mov     r8, rbx
0x140009485  lea     rdx, aDoneValidating_1; "Done validating partition/ramdisk %ws"
0x14000948c  mov     ecx, 2
0x140009491  mov     edi, eax
0x140009493  call    BfspLogMessage
0x140009498  jmp     short loc_1400094FC
0x14000949a  lea     rbx, [r14+14h]
0x14000949e  mov     r8, rbx
0x1400094a1  lea     rdx, aMovingToPartit; "Moving to Partition node with path %ws"
0x1400094a8  call    BfspLogMessage
0x1400094ad  mov     r8, rsi
0x1400094b0  mov     rdx, rbx
0x1400094b3  mov     rcx, r13
0x1400094b6  call    BfspFileExistsOnNtDevice
0x1400094bb  mov     r8, rbx
0x1400094be  lea     rdx, aDoneValidating_4; "Done validating partition %ws"
0x1400094c5  mov     ecx, 2
0x1400094ca  mov     edi, eax
0x1400094cc  call    BfspLogMessage
0x1400094d1  mov     rcx, [rbp+Handle]; Handle
0x1400094d5  test    rcx, rcx
0x1400094d8  jz      short loc_1400094DF
0x1400094da  call    BcdCloseObject
0x1400094df  mov     rbx, [rbp+var_10]
0x1400094e3  test    rbx, rbx
0x1400094e6  jz      short loc_1400094FC
0x1400094e8  call    cs:__imp_GetProcessHeap
0x1400094ee  mov     r8, rbx; lpMem
0x1400094f1  xor     edx, edx; dwFlags
0x1400094f3  mov     rcx, rax; hHeap
0x1400094f6  call    cs:__imp_HeapFree
0x1400094fc  lea     rdx, aReturningFromD; "Returning from device validation"
0x140009503  mov     ecx, 2
0x140009508  call    BfspLogMessage
0x14000950d  mov     eax, edi
0x14000950f  add     rsp, 48h
0x140009513  pop     r15
0x140009515  pop     r14
0x140009517  pop     r13
0x140009519  pop     r12
0x14000951b  pop     rdi
0x14000951c  pop     rsi
0x14000951d  pop     rbx
0x14000951e  pop     rbp
0x14000951f  retn
```
