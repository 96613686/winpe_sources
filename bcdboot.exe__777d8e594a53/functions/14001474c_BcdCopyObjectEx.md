# BcdCopyObjectEx

- ea: `0x14001474c`
- end: `0x140014ebf`
- name: `BcdCopyObjectEx`
- size: `1907`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int128 *, _QWORD *)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x140005b98`
- `0x140005fc4`
- `0x14001474c`
- `0x140014ec8`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x140013b9c`
- `0x140013ee8`
- `0x140014130`
- `0x140014574`
- `0x140014650`
- `0x14001474c`
- `0x140015090`
- `0x1400186fc`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x14001ae94`
- `0x14001c014`
- `0x14001c794`
- `0x14001f324`
- `0x140020720`
- `0x1400209d0`
- `0x140026650`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400149b9`
- `ntdll!RtlAllocateHeap` at `0x140014bbb`
- `ntdll!RtlAllocateHeap` at `0x1400149b9`
- `ntdll!RtlAllocateHeap` at `0x140014bbb`
- `ntdll!RtlFreeHeap` at `0x140014db0`
- `ntdll!RtlFreeHeap` at `0x140014dce`
- `ntdll!RtlFreeHeap` at `0x140014def`
- `ntdll!RtlFreeHeap` at `0x140014e2d`
- `ntdll!RtlFreeHeap` at `0x140014db0`
- `ntdll!RtlFreeHeap` at `0x140014dce`
- `ntdll!RtlFreeHeap` at `0x140014def`
- `ntdll!RtlFreeHeap` at `0x140014e2d`

## string_xrefs

- `0x140014800`: `Copying object. Flags: 0x%x`
- `0x140014b5f`: `BcdCopyObjectEx: Failed to set firmware object. Target: %ws Flags: 0x%x Status: %x`
- `0x140014bf7`: `BcdCopyObjectEx: Failed to enumerate source elements. Target: %ws Flags: 0x%x Status: %x`
- `0x140014e62`: `BcdCopyObjectEx: Failed to set target elements. Target: %ws Flags: 0x%x Element type: %lu Status: %x`
- `0x140014e51`: `BcdCopyObjectEx: Failed to copy object. Target: %ws Flags: 0x%x Status: %x`
- `0x1400148af`: `BcdCopyObjectEx: Failed to get object description Flags: 0x%x Status: %x`
- `0x140014a70`: `BcdCopyObjectEx: Failed to get generate object guid. Flags: 0x%x Status: %x`
- `0x140014aa3`: `BcdCopyObjectEx: Failed to get object identifier. Flags: 0x%x Status: %x`
- `0x140014b0f`: `BcdCopyObjectEx: Failed to create object. Target: %ws Flags: 0x%x  Status: %x`

## pseudocode

```c
__int64 __fastcall BcdCopyObjectEx(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int128 *a5, _QWORD *a6)
{
  __int64 v8; // r12
  void *v10; // rsi
  PVOID v11; // r13
  __int64 v12; // rax
  unsigned int v13; // edx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // ebx
  int ObjectDescription; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // edx
  unsigned int v22; // r12d
  int v23; // eax
  int v24; // edx
  unsigned int v25; // r14d
  unsigned int v26; // ebx
  __int64 v27; // rcx
  int v28; // r8d
  int v29; // eax
  int ObjectIdentifier; // eax
  int Object; // eax
  int v32; // eax
  _QWORD *Heap; // r14
  __int64 v34; // r8
  int v35; // edx
  unsigned int v36; // eax
  int v37; // edx
  __int64 v38; // r15
  _DWORD *v39; // rbx
  char *v40; // r12
  __int64 v41; // rdx
  int v42; // eax
  int v43; // ebx
  __int64 v44; // rax
  unsigned int v45; // r12d
  unsigned int v46; // r15d
  unsigned int v47; // r12d
  int v48; // eax
  HANDLE v49; // rcx
  __int64 v50; // [rsp+20h] [rbp-E0h]
  __int64 v51; // [rsp+20h] [rbp-E0h]
  __int64 v52; // [rsp+20h] [rbp-E0h]
  __int64 v53; // [rsp+20h] [rbp-E0h]
  __int64 v54; // [rsp+28h] [rbp-D8h]
  unsigned int Size; // [rsp+30h] [rbp-D0h] BYREF
  char Size_4; // [rsp+34h] [rbp-CCh]
  unsigned int v57; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v58; // [rsp+3Ch] [rbp-C4h] BYREF
  void *v59; // [rsp+40h] [rbp-C0h] BYREF
  char *v60; // [rsp+48h] [rbp-B8h] BYREF
  int v61; // [rsp+50h] [rbp-B0h]
  __int64 v62; // [rsp+58h] [rbp-A8h]
  HANDLE v63; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  char *v66; // [rsp+78h] [rbp-88h]
  __int64 v67; // [rsp+80h] [rbp-80h]
  PVOID v68; // [rsp+88h] [rbp-78h] BYREF
  __int64 v69; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h]
  _QWORD *v71; // [rsp+A0h] [rbp-60h]
  __int128 v72; // [rsp+A8h] [rbp-58h] BYREF
  char v73; // [rsp+C0h] [rbp-40h] BYREF

  v67 = a1;
  v62 = a4;
  v71 = a6;
  v57 = 0;
  v8 = a4;
  *a6 = 0;
  v58 = 0;
  v10 = 0;
  v65 = 5111808;
  v11 = 0;
  v66 = &v73;
  Size = 0;
  v69 = 0;
  v59 = 0;
  v68 = 0;
  Handle = 0;
  v63 = 0;
  v60 = 0;
  v72 = 0;
  if ( a1 && a2 && a4 )
  {
    v12 = BiLogMessage(2, L"Copying object. Flags: 0x%x");
    v13 = 0;
    v14 = a3 & 0x32;
    if ( (a3 & 0x32) == 0 )
      goto LABEL_8;
    do
    {
      LODWORD(v12) = v14 - 1;
      ++v13;
      v14 = ((_DWORD)v14 - 1) & (unsigned int)v14;
    }
    while ( (_DWORD)v14 );
    if ( v13 <= 1 )
    {
LABEL_8:
      if ( !a5 || (a3 & 1) == 0 )
      {
        if ( a1 != v8 || a5 || (LODWORD(v12) = a3, (a3 & 3) != 2) )
        {
          LOBYTE(v12) = 0;
          v61 = v12;
          if ( (a1 & 1) != 0 )
          {
            LOBYTE(v12) = (v8 & 1) != 0;
            v61 = (unsigned __int8)v12;
          }
          LOBYTE(v14) = v12;
          v15 = BiAcquireBcdSyncMutant(v14);
          v16 = v15;
          if ( v15 < 0 )
          {
            BiLogMessage(4, L"Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v15);
            return (unsigned int)v16;
          }
          Size_4 = 0;
          ObjectDescription = BiGetObjectDescription(a2, &v69);
          v16 = ObjectDescription;
          if ( ObjectDescription < 0 )
          {
            BiLogMessage(
              4,
              L"BcdCopyObjectEx: Failed to get object description Flags: 0x%x Status: %x",
              a3,
              (unsigned int)ObjectDescription);
LABEL_88:
            v49 = Handle;
            if ( Handle )
              BcdCloseObject(Handle);
            if ( v63 )
              BcdCloseObject(v63);
            if ( v11 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
            if ( v16 < 0 && v10 )
            {
              if ( Size_4 )
                BcdDeleteObject(v10);
              else
                BcdCloseObject(v10);
            }
            LOBYTE(v49) = v61;
            BiReleaseBcdSyncMutant(v49);
            return (unsigned int)v16;
          }
          BiGetRegistryValue(a2, L"FirmwareVariable", L"Description", 3, &v60, &v58);
          if ( a5 )
          {
            v72 = *a5;
            goto LABEL_21;
          }
          if ( (a3 & 1) != 0 )
          {
            v29 = BiGenerateObjectGuid(v8, &v72);
            v16 = v29;
            if ( v29 < 0 )
            {
              BiLogMessage(
                4,
                L"BcdCopyObjectEx: Failed to get generate object guid. Flags: 0x%x Status: %x",
                a3,
                (unsigned int)v29);
LABEL_43:
              v11 = v60;
              goto LABEL_88;
            }
          }
          else
          {
            ObjectIdentifier = BiGetObjectIdentifier(a2, &v72);
            v16 = ObjectIdentifier;
            if ( ObjectIdentifier < 0 )
            {
              BiLogMessage(
                4,
                L"BcdCopyObjectEx: Failed to get object identifier. Flags: 0x%x Status: %x",
                a3,
                (unsigned int)ObjectIdentifier);
              goto LABEL_43;
            }
          }
LABEL_21:
          P = 0;
          BiStringFromGUID(&v72, &v65);
          if ( (a3 & 2) == 0 && (a3 & 0x20) == 0 || (v20 = BcdOpenObject(v8, &v72, &v59), v10 = v59, v20 < 0) )
          {
LABEL_48:
            v11 = v60;
            if ( !v10 )
            {
              if ( (int)BcdOpenObject(v8, &v72, &v59) < 0 )
              {
                Object = BiCreateObject(v8, (unsigned int)&v72, (unsigned int)&v69, (a3 >> 2) & 1, (__int64)&v59);
                v16 = Object;
                if ( Object < 0 )
                {
                  LODWORD(v50) = Object;
                  BiLogMessage(
                    4,
                    L"BcdCopyObjectEx: Failed to create object. Target: %ws Flags: 0x%x  Status: %x",
                    v66,
                    (a3 >> 2) & 1,
                    v50);
                  v10 = v59;
                  goto LABEL_84;
                }
                Size_4 = 1;
              }
              v10 = v59;
            }
            if ( !v11 || (v32 = BiSaveFirmwareVariable(v10, &v72, v11, v58), v16 = v32, v32 >= 0) )
            {
              Heap = 0;
              Size = 0;
              v16 = BcdEnumerateElementsWithFlags(a2, v19, 0, (unsigned int)&Size, (__int64)&v57);
              if ( v16 == -1073741789 )
              {
                Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
                if ( !Heap )
                {
                  v16 = -1073741801;
                  goto LABEL_84;
                }
                v16 = BcdEnumerateElementsWithFlags(a2, v35, (_DWORD)Heap, (unsigned int)&Size, (__int64)&v57);
              }
              if ( v16 >= 0 )
              {
                v36 = 0;
                LODWORD(v59) = 0;
                if ( v57 )
                {
                  v37 = a3 & 8;
                  v58 = v37;
                  do
                  {
                    v38 = Heap[2 * v36];
                    v39 = (_DWORD *)(v38 + 4);
                    if ( !v37 || (*v39 & 0xF0000000) != 0x40000000 )
                    {
                      v40 = (char *)Heap[2 * v36 + 1];
                      v60 = v40;
                      if ( ((a3 & 0x10) == 0 || *v39 == 369098784) && (a3 & 0x20) == 0
                        || (v41 = (unsigned int)*v39,
                            Size = 0,
                            (unsigned int)BcdGetElementDataWithFlags(v10, v41, v34, 0, &Size) != -1073741789) )
                      {
                        v42 = BcdSetElementDataWithFlags(v10, (unsigned int)*v39, a3, v40, *(_DWORD *)(v38 + 8));
                        v16 = v42;
                        if ( v42 < 0 )
                        {
                          LODWORD(v54) = v42;
                          LODWORD(v52) = *(_DWORD *)(v38 + 4);
                          BiLogMessage(
                            4,
                            L"BcdCopyObjectEx: Failed to set target elements. Target: %ws Flags: 0x%x Element type: %lu Status: %x",
                            v66,
                            a3,
                            v52,
                            v54);
                          goto LABEL_82;
                        }
                      }
                      if ( *(_DWORD *)(v38 + 4) == 335544326 )
                      {
                        v43 = v62;
                        v44 = v67;
                        if ( v67 != v62 )
                        {
                          v45 = *(_DWORD *)(v38 + 8);
                          v46 = 0;
                          v47 = v45 >> 4;
                          if ( v47 )
                          {
                            do
                            {
                              if ( (int)BcdOpenObject(v44, &v60[16 * v46], &v63) >= 0 )
                              {
                                v48 = BcdCopyObjectEx(v67, (_DWORD)v63, a3 & 0xFFFFFFFE, v43, 0, (__int64)&Handle);
                                v16 = v48;
                                if ( v48 < 0 )
                                {
                                  LODWORD(v53) = v48;
                                  BiLogMessage(
                                    4,
                                    L"BcdCopyObjectEx: Failed to copy object. Target: %ws Flags: 0x%x Status: %x",
                                    v66,
                                    a3,
                                    v53);
                                  goto LABEL_82;
                                }
                                BcdCloseObject(Handle);
                                Handle = 0;
                                BcdCloseObject(v63);
                                v43 = v62;
                                v63 = 0;
                              }
                              v44 = v67;
                              ++v46;
                            }
                            while ( v46 < v47 );
                          }
                        }
                      }
                      v37 = v58;
                    }
                    v36 = (_DWORD)v59 + 1;
                    LODWORD(v59) = v36;
                  }
                  while ( v36 < v57 );
                }
                v16 = 0;
                *v71 = v10;
              }
              else
              {
                LODWORD(v51) = v16;
                BiLogMessage(
                  4,
                  L"BcdCopyObjectEx: Failed to enumerate source elements. Target: %ws Flags: 0x%x Status: %x",
                  v66,
                  a3,
                  v51);
              }
LABEL_82:
              if ( Heap )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              goto LABEL_84;
            }
            LODWORD(v50) = v32;
            BiLogMessage(
              4,
              L"BcdCopyObjectEx: Failed to set firmware object. Target: %ws Flags: 0x%x Status: %x",
              v66,
              a3,
              v50);
LABEL_84:
            if ( P )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            if ( v68 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v68);
            goto LABEL_88;
          }
          if ( (a3 & 0x20) == 0 || (int)BiGetElementData(a2, v19, &v68, &Size) < 0 || !Size )
            goto LABEL_46;
          v22 = Size >> 3;
          Size = 0;
          v23 = BcdEnumerateElementsWithFlags((_DWORD)v10, v21, 0, (unsigned int)&Size, (__int64)&v57);
          if ( v23 == -1073741789 )
          {
            P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
            v11 = P;
            if ( !P )
              goto LABEL_46;
            v23 = BcdEnumerateElementsWithFlags((_DWORD)v10, v24, (_DWORD)P, (unsigned int)&Size, (__int64)&v57);
          }
          if ( v23 >= 0 )
          {
            v25 = v57;
            if ( v57 )
            {
              v26 = 0;
              do
              {
                v27 = 0;
                v19 = *((_QWORD *)v11 + 2 * v26);
                if ( v22 )
                {
                  while ( 1 )
                  {
                    v28 = *((_DWORD *)v68 + 2 * v27);
                    if ( v28 == 1174405127 || v28 == *(_DWORD *)(v19 + 4) )
                      break;
                    v27 = (unsigned int)(v27 + 1);
                    if ( (unsigned int)v27 >= v22 )
                      goto LABEL_37;
                  }
                }
                else
                {
LABEL_37:
                  if ( (int)BiDeleteElement(v10, *(unsigned int *)(v19 + 4), 0) < 0 )
                    goto LABEL_46;
                }
                ++v26;
              }
              while ( v26 < v25 );
              goto LABEL_47;
            }
          }
LABEL_46:
          BcdDeleteObject(v10);
          v10 = 0;
          v59 = 0;
LABEL_47:
          v8 = v62;
          goto LABEL_48;
        }
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14001474c  push    rbp
0x14001474e  push    rbx
0x14001474f  push    rsi
0x140014750  push    rdi
0x140014751  push    r12
0x140014753  push    r13
0x140014755  push    r14
0x140014757  push    r15
0x140014759  lea     rbp, [rsp-28h]
0x14001475e  sub     rsp, 128h
0x140014765  mov     rax, cs:__security_cookie
0x14001476c  xor     rax, rsp
0x14001476f  mov     [rbp+60h+var_50], rax
0x140014773  mov     r14, [rbp+60h+arg_20]
0x14001477a  lea     rax, [rbp+60h+var_A0]
0x14001477e  mov     rbx, rcx
0x140014781  mov     [rbp+60h+var_E0], rcx
0x140014785  mov     rcx, [rbp+60h+arg_28]
0x14001478c  mov     r15, rdx
0x14001478f  xor     edx, edx
0x140014791  mov     [rsp+160h+var_108], r9
0x140014796  mov     [rbp+60h+var_C0], rcx
0x14001479a  xorps   xmm0, xmm0
0x14001479d  mov     [rsp+160h+var_128], edx
0x1400147a1  mov     r12, r9
0x1400147a4  mov     [rcx], rdx
0x1400147a7  mov     edi, r8d
0x1400147aa  mov     [rsp+160h+var_124], edx
0x1400147ae  mov     esi, edx
0x1400147b0  mov     [rsp+160h+var_F0], 4E0000h
0x1400147b9  mov     r13d, edx
0x1400147bc  mov     [rsp+160h+var_E8], rax
0x1400147c1  mov     dword ptr [rsp+160h+Size], edx
0x1400147c5  mov     [rbp+60h+var_D0], rdx
0x1400147c9  mov     [rsp+160h+var_120], rdx
0x1400147ce  mov     [rbp+60h+var_D8], rdx
0x1400147d2  mov     [rsp+160h+Handle], rdx
0x1400147d7  mov     [rsp+160h+var_100], rdx
0x1400147dc  mov     [rsp+160h+var_118], rdx
0x1400147e1  movups  [rbp+60h+var_B8], xmm0
0x1400147e5  test    rbx, rbx
0x1400147e8  jz      loc_140014E9A
0x1400147ee  test    r15, r15
0x1400147f1  jz      loc_140014E9A
0x1400147f7  test    r9, r9
0x1400147fa  jz      loc_140014E9A
0x140014800  lea     rdx, aCopyingObjectF; "Copying object. Flags: 0x%x"
0x140014807  lea     ecx, [r13+2]
0x14001480b  call    BiLogMessage
0x140014810  mov     ecx, edi
0x140014812  lea     r8d, [r13+1]
0x140014816  mov     edx, esi
0x140014818  and     ecx, 32h
0x14001481b  jz      short loc_140014830
0x14001481d  lea     eax, [rcx-1]
0x140014820  add     edx, r8d
0x140014823  and     ecx, eax
0x140014825  jnz     short loc_14001481D
0x140014827  cmp     edx, r8d
0x14001482a  ja      loc_140014E9A
0x140014830  test    r14, r14
0x140014833  jz      short loc_14001483E
0x140014835  test    r8b, dil
0x140014838  jnz     loc_140014E9A
0x14001483e  cmp     rbx, r12
0x140014841  jnz     short loc_140014854
0x140014843  test    r14, r14
0x140014846  jnz     short loc_140014854
0x140014848  mov     eax, edi
0x14001484a  and     al, 3
0x14001484c  cmp     al, 2
0x14001484e  jz      loc_140014E9A
0x140014854  xor     al, al
0x140014856  mov     [rsp+160h+var_110], eax
0x14001485a  test    r8b, bl
0x14001485d  jz      short loc_14001486D
0x14001485f  test    r8b, r12b
0x140014862  movzx   eax, al
0x140014865  cmovnz  eax, r8d
0x140014869  mov     [rsp+160h+var_110], eax
0x14001486d  mov     cl, al
0x14001486f  call    BiAcquireBcdSyncMutant
0x140014874  mov     ebx, eax
0x140014876  test    eax, eax
0x140014878  jns     short loc_140014895
0x14001487a  mov     r8d, eax
0x14001487d  lea     rdx, aFailedToAcquir_0; "Failed to acquire BCD sync mutant. Stat"...
0x140014884  mov     ecx, 4
0x140014889  call    BiLogMessage
0x14001488e  mov     eax, ebx
0x140014890  jmp     loc_140014E9F
0x140014895  lea     rdx, [rbp+60h+var_D0]
0x140014899  mov     byte ptr [rsp+160h+Size+4], sil
0x14001489e  mov     rcx, r15
0x1400148a1  call    BiGetObjectDescription
0x1400148a6  mov     ebx, eax
0x1400148a8  test    eax, eax
0x1400148aa  jns     short loc_1400148C8
0x1400148ac  mov     r9d, eax
0x1400148af  lea     rdx, aBcdcopyobjecte_2; "BcdCopyObjectEx: Failed to get object d"...
0x1400148b6  mov     r8d, edi
0x1400148b9  mov     ecx, 4
0x1400148be  call    BiLogMessage
0x1400148c3  jmp     loc_140014DF5
0x1400148c8  lea     rax, [rsp+160h+var_124]
0x1400148cd  mov     r9d, 3
0x1400148d3  mov     [rsp+160h+var_138], rax
0x1400148d8  lea     r8, aDescription; "Description"
0x1400148df  lea     rax, [rsp+160h+var_118]
0x1400148e4  mov     rcx, r15
0x1400148e7  lea     rdx, aFirmwarevariab; "FirmwareVariable"
0x1400148ee  mov     [rsp+160h+var_140], rax
0x1400148f3  call    BiGetRegistryValue
0x1400148f8  test    r14, r14
0x1400148fb  jz      loc_140014A54
0x140014901  movups  xmm0, xmmword ptr [r14]
0x140014905  movdqu  [rbp+60h+var_B8], xmm0
0x14001490a  lea     rdx, [rsp+160h+var_F0]
0x14001490f  mov     [rbp+60h+P], r13
0x140014913  lea     rcx, [rbp+60h+var_B8]
0x140014917  call    BiStringFromGUID
0x14001491c  test    dil, 2
0x140014920  jnz     short loc_14001492C
0x140014922  test    dil, 20h
0x140014926  jz      loc_140014AC0
0x14001492c  lea     r8, [rsp+160h+var_120]
0x140014931  mov     rcx, r12
0x140014934  lea     rdx, [rbp+60h+var_B8]
0x140014938  call    BcdOpenObject
0x14001493d  mov     rsi, [rsp+160h+var_120]
0x140014942  test    eax, eax
0x140014944  js      loc_140014AC0
0x14001494a  test    dil, 20h
0x14001494e  jz      loc_140014AAC
0x140014954  lea     r9, [rsp+160h+Size]
0x140014959  mov     rcx, r15
0x14001495c  lea     r8, [rbp+60h+var_D8]
0x140014960  call    BiGetElementData
0x140014965  test    eax, eax
0x140014967  js      loc_140014AAC
0x14001496d  mov     eax, dword ptr [rsp+160h+Size]
0x140014971  test    eax, eax
0x140014973  jz      loc_140014AAC
0x140014979  shr     eax, 3
0x14001497c  lea     r9, [rsp+160h+Size]
0x140014981  mov     r12d, eax
0x140014984  mov     dword ptr [rsp+160h+Size], r13d
0x140014989  lea     rax, [rsp+160h+var_128]
0x14001498e  xor     r8d, r8d
0x140014991  mov     rcx, rsi
0x140014994  mov     [rsp+160h+var_140], rax
0x140014999  call    BcdEnumerateElementsWithFlags
0x14001499e  cmp     eax, 0C0000023h
0x1400149a3  jnz     short loc_1400149E9
0x1400149a5  mov     rcx, gs:60h
0x1400149ae  xor     edx, edx; Flags
0x1400149b0  mov     r8d, dword ptr [rsp+160h+Size]; Size
0x1400149b5  mov     rcx, [rcx+30h]; HeapHandle
0x1400149b9  call    cs:__imp_RtlAllocateHeap
0x1400149bf  mov     [rbp+60h+P], rax
0x1400149c3  mov     r13, rax
0x1400149c6  test    rax, rax
0x1400149c9  jz      loc_140014AAC
0x1400149cf  lea     rax, [rsp+160h+var_128]
0x1400149d4  mov     r8, r13
0x1400149d7  lea     r9, [rsp+160h+Size]
0x1400149dc  mov     [rsp+160h+var_140], rax
0x1400149e1  mov     rcx, rsi
0x1400149e4  call    BcdEnumerateElementsWithFlags
0x1400149e9  test    eax, eax
0x1400149eb  js      loc_140014AAC
0x1400149f1  mov     r14d, [rsp+160h+var_128]
0x1400149f6  test    r14d, r14d
0x1400149f9  jz      loc_140014AAC
0x1400149ff  xor     ebx, ebx
0x140014a01  test    r14d, r14d
0x140014a04  jz      loc_140014ABB
0x140014a0a  mov     eax, ebx
0x140014a0c  xor     ecx, ecx
0x140014a0e  add     rax, rax
0x140014a11  mov     rdx, [r13+rax*8+0]
0x140014a16  test    r12d, r12d
0x140014a19  jz      short loc_140014A39
0x140014a1b  mov     r8, [rbp+60h+var_D8]
0x140014a1f  mov     r8d, [r8+rcx*8]
0x140014a23  cmp     r8d, 46000007h
0x140014a2a  jz      short loc_140014A4B
0x140014a2c  cmp     r8d, [rdx+4]
0x140014a30  jz      short loc_140014A4B
0x140014a32  inc     ecx
0x140014a34  cmp     ecx, r12d
0x140014a37  jb      short loc_140014A1B
0x140014a39  mov     edx, [rdx+4]
0x140014a3c  xor     r8d, r8d
0x140014a3f  mov     rcx, rsi
0x140014a42  call    BiDeleteElement
0x140014a47  test    eax, eax
0x140014a49  js      short loc_140014AAC
0x140014a4b  inc     ebx
0x140014a4d  cmp     ebx, r14d
0x140014a50  jb      short loc_140014A0A
0x140014a52  jmp     short loc_140014ABB
0x140014a54  lea     rdx, [rbp+60h+var_B8]
0x140014a58  test    dil, 1
0x140014a5c  jz      short loc_140014A91
0x140014a5e  mov     rcx, r12
0x140014a61  call    BiGenerateObjectGuid
0x140014a66  mov     ebx, eax
0x140014a68  test    eax, eax
0x140014a6a  jns     loc_14001490A
0x140014a70  lea     rdx, aBcdcopyobjecte_3; "BcdCopyObjectEx: Failed to get generate"...
0x140014a77  mov     r8d, edi
0x140014a7a  mov     r9d, eax
0x140014a7d  mov     ecx, 4
0x140014a82  call    BiLogMessage
0x140014a87  mov     r13, [rsp+160h+var_118]
0x140014a8c  jmp     loc_140014DF5
0x140014a91  mov     rcx, r15
0x140014a94  call    BiGetObjectIdentifier
0x140014a99  mov     ebx, eax
0x140014a9b  test    eax, eax
0x140014a9d  jns     loc_14001490A
0x140014aa3  lea     rdx, aBcdcopyobjecte_0; "BcdCopyObjectEx: Failed to get object i"...
0x140014aaa  jmp     short loc_140014A77
0x140014aac  mov     rcx, rsi
0x140014aaf  call    BcdDeleteObject
0x140014ab4  xor     esi, esi
0x140014ab6  mov     [rsp+160h+var_120], rsi
0x140014abb  mov     r12, [rsp+160h+var_108]
0x140014ac0  mov     r13, [rsp+160h+var_118]
0x140014ac5  test    rsi, rsi
0x140014ac8  jnz     short loc_140014B3B
0x140014aca  lea     r8, [rsp+160h+var_120]
0x140014acf  mov     rcx, r12
0x140014ad2  lea     rdx, [rbp+60h+var_B8]
0x140014ad6  call    BcdOpenObject
0x140014adb  test    eax, eax
0x140014add  jns     short loc_140014B36
0x140014adf  lea     rax, [rsp+160h+var_120]
0x140014ae4  mov     esi, edi
0x140014ae6  shr     esi, 2
0x140014ae9  lea     r8, [rbp+60h+var_D0]
0x140014aed  and     esi, 1
0x140014af0  mov     [rsp+160h+var_140], rax
0x140014af5  mov     r9d, esi
0x140014af8  lea     rdx, [rbp+60h+var_B8]
0x140014afc  mov     rcx, r12
0x140014aff  call    BiCreateObject
0x140014b04  mov     ebx, eax
0x140014b06  test    eax, eax
0x140014b08  jns     short loc_140014B31
0x140014b0a  mov     r8, [rsp+160h+var_E8]
0x140014b0f  lea     rdx, aBcdcopyobjecte_5; "BcdCopyObjectEx: Failed to create objec"...
0x140014b16  mov     r9d, esi
0x140014b19  mov     dword ptr [rsp+160h+var_140], eax
0x140014b1d  mov     ecx, 4
0x140014b22  call    BiLogMessage
0x140014b27  mov     rsi, [rsp+160h+var_120]
0x140014b2c  jmp     loc_140014DB6
0x140014b31  mov     byte ptr [rsp+160h+Size+4], 1
0x140014b36  mov     rsi, [rsp+160h+var_120]
0x140014b3b  test    r13, r13
0x140014b3e  jz      short loc_140014B7C
0x140014b40  mov     r9d, [rsp+160h+var_124]
0x140014b45  lea     rdx, [rbp+60h+var_B8]
0x140014b49  mov     r8, r13
0x140014b4c  mov     rcx, rsi
0x140014b4f  call    BiSaveFirmwareVariable
0x140014b54  mov     ebx, eax
0x140014b56  test    eax, eax
0x140014b58  jns     short loc_140014B7C
0x140014b5a  mov     r8, [rsp+160h+var_E8]
0x140014b5f  lea     rdx, aBcdcopyobjecte_4; "BcdCopyObjectEx: Failed to set firmware"...
0x140014b66  mov     r9d, edi
0x140014b69  mov     dword ptr [rsp+160h+var_140], eax
0x140014b6d  mov     ecx, 4
0x140014b72  call    BiLogMessage
0x140014b77  jmp     loc_140014DB6
0x140014b7c  lea     rax, [rsp+160h+var_128]
0x140014b81  xor     r14d, r14d
0x140014b84  lea     r9, [rsp+160h+Size]
0x140014b89  mov     dword ptr [rsp+160h+Size], r14d
0x140014b8e  xor     r8d, r8d
0x140014b91  mov     [rsp+160h+var_140], rax
0x140014b96  mov     rcx, r15
0x140014b99  call    BcdEnumerateElementsWithFlags
0x140014b9e  mov     ebx, eax
0x140014ba0  cmp     eax, 0C0000023h
0x140014ba5  jnz     short loc_140014BEF
0x140014ba7  mov     rcx, gs:60h
0x140014bb0  xor     edx, edx; Flags
0x140014bb2  mov     r8d, dword ptr [rsp+160h+Size]; Size
0x140014bb7  mov     rcx, [rcx+30h]; HeapHandle
0x140014bbb  call    cs:__imp_RtlAllocateHeap
0x140014bc1  mov     r14, rax
0x140014bc4  test    rax, rax
0x140014bc7  jnz     short loc_140014BD3
0x140014bc9  mov     ebx, 0C0000017h
0x140014bce  jmp     loc_140014DB6
0x140014bd3  lea     rax, [rsp+160h+var_128]
  ... truncated ...
```
