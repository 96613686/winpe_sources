# BfspRemoveDuplicateEntries

- ea: `0x140008104`
- end: `0x1400083fa`
- name: `BfspRemoveDuplicateEntries`
- size: `758`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003d30`
- `0x140007cdc`

## callees

- `0x140005100`
- `0x14000619c`
- `0x1400064c0`
- `0x140008104`
- `0x14000e628`
- `0x140013b48`
- `0x140013b9c`
- `0x140013ee8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400083a3`
- `KERNEL32!HeapFree` at `0x1400083a3`
- `KERNEL32!GetProcessHeap` at `0x140008395`
- `KERNEL32!GetProcessHeap` at `0x140008395`
- `ntdll!RtlStringFromGUID` at `0x1400082be`
- `ntdll!RtlStringFromGUID` at `0x1400082be`
- `ntdll!RtlFreeUnicodeString` at `0x1400082dd`
- `ntdll!RtlFreeUnicodeString` at `0x1400082dd`
- `ntdll!RtlInitUnicodeString` at `0x14000814e`
- `ntdll!RtlInitUnicodeString` at `0x14000814e`

## string_xrefs

- `0x14000818d`: `Failed to open a handle to the OS loader element. Status = [%x]`
- `0x1400083cd`: `Failed to delete duplicate loader object. Status = [%x]`
- `0x140008363`: `Failed to remove duplicate object from bootmgr display order. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspRemoveDuplicateEntries(__int64 a1, _QWORD *a2)
{
  HANDLE v2; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  _QWORD *v9; // r12
  __int64 i; // r14
  _QWORD *v11; // rsi
  int v12; // eax
  HANDLE v13; // rbx
  int v14; // eax
  char v15; // dl
  GUID v16; // xmm0
  unsigned __int64 v17; // rcx
  char v18; // al
  int v19; // eax
  __int64 v20; // rdx
  int v21; // ebx
  __m128i v22; // xmm0
  HANDLE ProcessHeap; // rax
  HANDLE Handle; // [rsp+30h] [rbp-40h] BYREF
  HANDLE v25; // [rsp+38h] [rbp-38h] BYREF
  HANDLE v26; // [rsp+40h] [rbp-30h] BYREF
  _DWORD v27[2]; // [rsp+48h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  char v31; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v32; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  v26 = 0;
  Handle = 0;
  lpMem = 0;
  v25 = 0;
  v31 = 0;
  v32 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( (dword_14003F8FC & 4) == 0 )
    return 0;
  BfspLogMessage(2, L"Removing duplicate entries.");
  v6 = BcdOpenObject(a1, a2, &v25);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v27[0] = 1;
    v27[1] = 270532611;
    v8 = BfspEnumerateObjects(a1, (int)v27, &v32, &lpMem);
    v9 = lpMem;
    v7 = v8;
    if ( v8 >= 0 )
    {
      for ( i = 0; (unsigned int)i < v32; i = (unsigned int)(i + 1) )
      {
        v11 = &v9[3 * i];
        if ( *v11 != *a2 || v11[1] != a2[1] )
        {
          v12 = BcdOpenObject(a1, &v9[3 * i], &Handle);
          v7 = v12;
          if ( v12 < 0 )
          {
            BfspLogMessage(4, L"Failed to get a handle to the OS loader. Status = [%x]", (unsigned int)v12);
            v2 = Handle;
            goto LABEL_34;
          }
          v13 = Handle;
          v14 = BfspCompareObjects((__int64)v25, (__int64)Handle, (__int64)CompareElementListOsLoader, 4u, &v31);
          v15 = v31;
          if ( v14 < 0 )
            v15 = 0;
          v31 = v15;
          if ( (dword_14003F8FC & 1) == 0 )
          {
            if ( byte_14003F8F8 )
              v16 = GUID_WINDOWS_SETUP_EFI;
            else
              v16 = GUID_WINDOWS_SETUP_PCAT;
            v17 = *v11 - *(_QWORD *)&v16.Data1;
            if ( *v11 == *(_QWORD *)&v16.Data1 )
              v17 = v11[1] - _mm_srli_si128((__m128i)v16, 8).m128i_u64[0];
            v18 = v15;
            if ( !v17 )
              v18 = 1;
            v15 = v18;
            v31 = v18;
          }
          if ( v15 )
          {
            RtlStringFromGUID((const GUID *const)&v9[3 * i], &DestinationString);
            BfspLogMessage(2, L"Removing duplicate object %wZ", &DestinationString);
            RtlFreeUnicodeString(&DestinationString);
            v19 = BcdDeleteObject((__int64)v13);
            v2 = 0;
            v7 = v19;
            Handle = 0;
            if ( v19 < 0 )
            {
              BfspLogMessage(4, L"Failed to delete duplicate loader object. Status = [%x]", (unsigned int)v19);
              goto LABEL_36;
            }
            if ( (int)BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v26) >= 0 )
            {
              v21 = BfspDeleteObjectFromDisplayOrder((__int64)v26, v20, (__int64)&v9[3 * i]);
              BcdCloseObject(v26);
              if ( v21 < 0 )
              {
                if ( byte_14003F8F8 )
                  v22 = (__m128i)GUID_WINDOWS_SETUP_EFI;
                else
                  v22 = (__m128i)GUID_WINDOWS_SETUP_PCAT;
                if ( *v11 != v22.m128i_i64[0] || v11[1] != _mm_srli_si128(v22, 8).m128i_u64[0] )
                  BfspLogMessage(
                    3,
                    L"Failed to remove duplicate object from bootmgr display order. Status = [%x]",
                    (unsigned int)v21);
              }
            }
          }
          else
          {
            BcdCloseObject(v13);
            v2 = 0;
            Handle = 0;
          }
        }
      }
      v7 = 0;
LABEL_34:
      if ( v2 )
        BcdCloseObject(v2);
    }
LABEL_36:
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  else
  {
    BfspLogMessage(4, L"Failed to open a handle to the OS loader element. Status = [%x]", (unsigned int)v6);
  }
  if ( v25 )
    BcdCloseObject(v25);
  return v7;
}

```

## disassembly

```asm
0x140008104  mov     [rsp-38h+arg_8], rdx
0x140008109  push    rbp
0x14000810a  push    rbx
0x14000810b  push    rsi
0x14000810c  push    rdi
0x14000810d  push    r12
0x14000810f  push    r14
0x140008111  push    r15
0x140008113  mov     rbp, rsp
0x140008116  sub     rsp, 70h
0x14000811a  xor     edi, edi
0x14000811c  mov     [rbp+var_30], 0
0x140008124  mov     rbx, rdx
0x140008127  mov     [rbp+Handle], rdi
0x14000812b  mov     r15, rcx
0x14000812e  mov     [rbp+lpMem], rdi
0x140008132  xorps   xmm0, xmm0
0x140008135  mov     [rbp+var_38], rdi
0x140008139  xor     edx, edx; SourceString
0x14000813b  mov     [rbp+arg_10], 0
0x14000813f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140008143  mov     [rbp+arg_18], 0
0x14000814a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000814e  call    cs:__imp_RtlInitUnicodeString
0x140008154  test    byte ptr cs:dword_14003F8FC, 4
0x14000815b  jnz     short loc_140008164
0x14000815d  xor     eax, eax
0x14000815f  jmp     loc_1400083BB
0x140008164  lea     rdx, aRemovingDuplic_0; "Removing duplicate entries."
0x14000816b  mov     ecx, 2
0x140008170  call    BfspLogMessage
0x140008175  lea     r8, [rbp+var_38]
0x140008179  mov     rdx, rbx
0x14000817c  mov     rcx, r15
0x14000817f  call    BcdOpenObject
0x140008184  mov     ebx, eax
0x140008186  test    eax, eax
0x140008188  jns     short loc_1400081A3
0x14000818a  mov     r8d, eax
0x14000818d  lea     rdx, aFailedToOpenAH_3; "Failed to open a handle to the OS loade"...
0x140008194  mov     ecx, 4
0x140008199  call    BfspLogMessage
0x14000819e  jmp     loc_1400083A9
0x1400081a3  lea     r9, [rbp+lpMem]
0x1400081a7  mov     [rbp+var_28], 1
0x1400081ae  lea     r8, [rbp+arg_18]
0x1400081b2  mov     [rbp+var_24], 10200003h
0x1400081b9  lea     rdx, [rbp+var_28]
0x1400081bd  mov     rcx, r15
0x1400081c0  call    BfspEnumerateObjects
0x1400081c5  mov     r12, [rbp+lpMem]
0x1400081c9  mov     ebx, eax
0x1400081cb  test    eax, eax
0x1400081cd  js      loc_140008390
0x1400081d3  xor     r14d, r14d
0x1400081d6  cmp     [rbp+arg_18], edi
0x1400081d9  jbe     loc_140008381
0x1400081df  lea     rcx, [r14+r14*2]
0x1400081e3  lea     rsi, [r12+rcx*8]
0x1400081e7  mov     rcx, [rbp+arg_8]
0x1400081eb  mov     rax, [rsi]
0x1400081ee  cmp     rax, [rcx]
0x1400081f1  jnz     short loc_140008201
0x1400081f3  mov     rax, [rsi+8]
0x1400081f7  cmp     rax, [rcx+8]
0x1400081fb  jz      loc_140008374
0x140008201  lea     r8, [rbp+Handle]
0x140008205  mov     rdx, rsi
0x140008208  mov     rcx, r15
0x14000820b  call    BcdOpenObject
0x140008210  mov     ebx, eax
0x140008212  test    eax, eax
0x140008214  js      loc_1400083E0
0x14000821a  mov     rbx, [rbp+Handle]
0x14000821e  lea     rax, [rbp+arg_10]
0x140008222  mov     rcx, [rbp+var_38]
0x140008226  lea     r8, CompareElementListOsLoader
0x14000822d  mov     rdx, rbx
0x140008230  mov     [rsp+70h+var_50], rax
0x140008235  mov     r9d, 4
0x14000823b  call    BfspCompareObjects
0x140008240  movzx   edx, [rbp+arg_10]
0x140008244  xor     ecx, ecx
0x140008246  test    eax, eax
0x140008248  cmovs   edx, ecx
0x14000824b  lea     r8d, [rcx+1]
0x14000824f  mov     [rbp+arg_10], dl
0x140008252  test    byte ptr cs:dword_14003F8FC, r8b
0x140008259  jnz     short loc_1400082A0
0x14000825b  cmp     cs:byte_14003F8F8, cl
0x140008261  jz      short loc_14000826C
0x140008263  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_EFI.Data1
0x14000826a  jmp     short loc_140008273
0x14000826c  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_PCAT.Data1
0x140008273  mov     rcx, [rsi]
0x140008276  movq    rax, xmm0
0x14000827b  sub     rcx, rax
0x14000827e  jnz     short loc_140008291
0x140008280  mov     rcx, [rsi+8]
0x140008284  psrldq  xmm0, 8
0x140008289  movq    rax, xmm0
0x14000828e  sub     rcx, rax
0x140008291  movzx   eax, dl
0x140008294  test    rcx, rcx
0x140008297  cmovz   eax, r8d
0x14000829b  mov     dl, al
0x14000829d  mov     [rbp+arg_10], al
0x1400082a0  test    dl, dl
0x1400082a2  jnz     short loc_1400082B7
0x1400082a4  mov     rcx, rbx; Handle
0x1400082a7  call    BcdCloseObject
0x1400082ac  xor     edi, edi
0x1400082ae  mov     [rbp+Handle], rdi
0x1400082b2  jmp     loc_140008374
0x1400082b7  lea     rdx, [rbp+DestinationString]; GuidString
0x1400082bb  mov     rcx, rsi; Guid
0x1400082be  call    cs:__imp_RtlStringFromGUID
0x1400082c4  lea     r8, [rbp+DestinationString]
0x1400082c8  mov     ecx, 2
0x1400082cd  lea     rdx, aRemovingDuplic; "Removing duplicate object %wZ"
0x1400082d4  call    BfspLogMessage
0x1400082d9  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1400082dd  call    cs:__imp_RtlFreeUnicodeString
0x1400082e3  mov     rcx, rbx
0x1400082e6  call    BcdDeleteObject
0x1400082eb  xor     edi, edi
0x1400082ed  mov     ebx, eax
0x1400082ef  mov     [rbp+Handle], rdi
0x1400082f3  test    eax, eax
0x1400082f5  js      loc_1400083CA
0x1400082fb  lea     r8, [rbp+var_30]
0x1400082ff  mov     rcx, r15
0x140008302  lea     rdx, GUID_WINDOWS_BOOTMGR
0x140008309  call    BcdOpenObject
0x14000830e  test    eax, eax
0x140008310  js      short loc_140008374
0x140008312  mov     rcx, [rbp+var_30]
0x140008316  mov     r8, rsi
0x140008319  call    BfspDeleteObjectFromDisplayOrder
0x14000831e  mov     rcx, [rbp+var_30]; Handle
0x140008322  mov     ebx, eax
0x140008324  call    BcdCloseObject
0x140008329  test    ebx, ebx
0x14000832b  jns     short loc_140008374
0x14000832d  cmp     cs:byte_14003F8F8, dil
0x140008334  jz      short loc_14000833F
0x140008336  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_EFI.Data1
0x14000833d  jmp     short loc_140008346
0x14000833f  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_SETUP_PCAT.Data1
0x140008346  movq    rax, xmm0
0x14000834b  cmp     [rsi], rax
0x14000834e  jnz     short loc_140008360
0x140008350  psrldq  xmm0, 8
0x140008355  movq    rax, xmm0
0x14000835a  cmp     [rsi+8], rax
0x14000835e  jz      short loc_140008374
0x140008360  mov     r8d, ebx
0x140008363  lea     rdx, aFailedToRemove; "Failed to remove duplicate object from "...
0x14000836a  mov     ecx, 3
0x14000836f  call    BfspLogMessage
0x140008374  inc     r14d
0x140008377  cmp     r14d, [rbp+arg_18]
0x14000837b  jb      loc_1400081DF
0x140008381  xor     ebx, ebx
0x140008383  test    rdi, rdi
0x140008386  jz      short loc_140008390
0x140008388  mov     rcx, rdi; Handle
0x14000838b  call    BcdCloseObject
0x140008390  test    r12, r12
0x140008393  jz      short loc_1400083A9
0x140008395  call    cs:__imp_GetProcessHeap
0x14000839b  mov     r8, r12; lpMem
0x14000839e  xor     edx, edx; dwFlags
0x1400083a0  mov     rcx, rax; hHeap
0x1400083a3  call    cs:__imp_HeapFree
0x1400083a9  cmp     [rbp+var_38], 0
0x1400083ae  jz      short loc_1400083B9
0x1400083b0  mov     rcx, [rbp+var_38]; Handle
0x1400083b4  call    BcdCloseObject
0x1400083b9  mov     eax, ebx
0x1400083bb  add     rsp, 70h
0x1400083bf  pop     r15
0x1400083c1  pop     r14
0x1400083c3  pop     r12
0x1400083c5  pop     rdi
0x1400083c6  pop     rsi
0x1400083c7  pop     rbx
0x1400083c8  pop     rbp
0x1400083c9  retn
0x1400083ca  mov     r8d, eax
0x1400083cd  lea     rdx, aFailedToDelete_5; "Failed to delete duplicate loader objec"...
0x1400083d4  mov     ecx, 4
0x1400083d9  call    BfspLogMessage
0x1400083de  jmp     short loc_140008390
0x1400083e0  mov     r8d, eax
0x1400083e3  lea     rdx, aFailedToGetAHa_1; "Failed to get a handle to the OS loader"...
0x1400083ea  mov     ecx, 4
0x1400083ef  call    BfspLogMessage
0x1400083f4  mov     rdi, [rbp+Handle]
0x1400083f8  jmp     short loc_140008383
```
