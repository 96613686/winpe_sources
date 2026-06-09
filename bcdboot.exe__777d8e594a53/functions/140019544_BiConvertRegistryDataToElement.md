# BiConvertRegistryDataToElement

- ea: `0x140019544`
- end: `0x140019989`
- name: `BiConvertRegistryDataToElement`
- size: `1093`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, unsigned int, int, GUID *Guid, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140018890`
- `0x140019bb8`

## callees

- `0x1400133e4`
- `0x140015160`
- `0x140015b54`
- `0x140015c48`
- `0x140019544`
- `0x14001a6b0`
- `0x140020e68`
- `0x1400265e2`
- `0x1400265ee`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400198d7`
- `ntdll!RtlFreeHeap` at `0x14001993e`
- `ntdll!RtlFreeHeap` at `0x14001997b`
- `ntdll!RtlFreeHeap` at `0x1400198d7`
- `ntdll!RtlFreeHeap` at `0x14001993e`
- `ntdll!RtlFreeHeap` at `0x14001997b`
- `ntdll!RtlInitUnicodeString` at `0x1400196eb`
- `ntdll!RtlInitUnicodeString` at `0x14001977f`
- `ntdll!RtlInitUnicodeString` at `0x1400196eb`
- `ntdll!RtlInitUnicodeString` at `0x14001977f`
- `ntdll!RtlGUIDFromString` at `0x1400196f8`
- `ntdll!RtlGUIDFromString` at `0x14001978d`
- `ntdll!RtlGUIDFromString` at `0x1400196f8`
- `ntdll!RtlGUIDFromString` at `0x14001978d`

## pseudocode

```c
__int64 __fastcall BiConvertRegistryDataToElement(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        GUID *Guid,
        unsigned int *a7)
{
  unsigned int *v7; // r15
  unsigned int v8; // r13d
  unsigned int v9; // edi
  const WCHAR *v11; // r14
  unsigned int v13; // esi
  NTSTATUS v14; // ebx
  GUID *v15; // rcx
  GUID *v16; // rcx
  __int64 v17; // r9
  const wchar_t *v18; // rdx
  GUID *v19; // r12
  __int64 v20; // rax
  char v22; // bl
  __int64 v23; // r12
  GUID *v24; // rdi
  void *v25; // rcx
  __int16 v26; // di
  int v27; // eax
  PVOID v28; // rcx
  __int64 v29; // rdx
  GUID *v30; // rbx
  int v31; // [rsp+30h] [rbp-38h] BYREF
  PVOID P; // [rsp+38h] [rbp-30h] BYREF
  void *v33; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-20h] BYREF
  size_t Size; // [rsp+C8h] [rbp+60h] BYREF

  v7 = a7;
  v8 = 0;
  v9 = a3;
  P = 0;
  LODWORD(Size) = 0;
  v33 = 0;
  v11 = (const WCHAR *)a2;
  v31 = 0;
  v13 = 0;
  DestinationString = 0;
  switch ( HIBYTE(a4) & 0xF )
  {
    case 1:
      v17 = 28;
      if ( a3 < 0x1C )
      {
        v18 = L"Insufficient length for BCD element. Length %lu Required %lu DataType: %lu";
        goto LABEL_27;
      }
      v25 = a2 + 4;
      v17 = a2[6] + 16LL;
      if ( v17 != a3 )
      {
        v18 = L"Unexpected length for BCD element. Length %lu Expected: %lu DataType: %lu";
        goto LABEL_27;
      }
      v26 = a5;
      if ( (a5 & 1) != 0 )
      {
        v27 = BiConvertBootEnvironmentDeviceToQualifiedPartition(v25, &P, &Size);
      }
      else if ( (a5 & 2) != 0 )
      {
        v27 = BiConvertBootEnvironmentDeviceToUnknown(v25);
      }
      else
      {
        v27 = BiConvertBootEnvironmentDeviceToNt((_DWORD)v25, a4, a5, (unsigned int)&P, (__int64)&Size);
      }
      v14 = v27;
      if ( v27 < 0 )
      {
LABEL_47:
        v13 = Size;
        if ( v14 != -1073741789 )
          return (unsigned int)v14;
LABEL_48:
        *v7 = v13;
        return (unsigned int)v14;
      }
      v28 = P;
      if ( *(_DWORD *)P != 8 )
        goto LABEL_75;
      if ( (v26 & 0x100) != 0 )
      {
        if ( (int)BiResolveLocate(P, a1, &v33, &v31) >= 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          v28 = v33;
          P = v33;
          LODWORD(Size) = v31;
          v33 = 0;
LABEL_75:
          if ( (unsigned int)Size > *v7 )
          {
            v14 = -1073741789;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            v13 = Size;
            goto LABEL_48;
          }
          v30 = Guid;
          memcpy_0(Guid, v28, (unsigned int)Size);
          *(GUID *)&v30->Data2 = *(GUID *)v11;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          goto LABEL_78;
        }
      }
      else if ( (int)BiResolveLocateDevice(a1, P) >= 0 )
      {
        v29 = *((unsigned int *)P + 6);
        LODWORD(Size) = Size - v29;
        memmove_0(P, (char *)P + v29, (unsigned int)Size);
      }
      v28 = P;
      goto LABEL_75;
    case 2:
      if ( a3 )
      {
        v22 = 1;
        if ( (a3 & 1) == 0 )
        {
          v13 = a3;
          v23 = a3;
          if ( *(_WORD *)((char *)a2 + a3 - 2) )
          {
            v9 = a3 + 2;
            v13 = a3 + 2;
          }
          else
          {
            v22 = 0;
          }
          if ( v9 > *a7 )
            goto LABEL_12;
          v24 = Guid;
          memcpy_0(Guid, a2, a3);
          if ( v22 )
            *(_WORD *)((char *)&v24->Data1 + v23) = 0;
LABEL_15:
          v14 = 0;
          goto LABEL_48;
        }
      }
      goto LABEL_42;
    case 3:
      v13 = 16;
      LODWORD(Size) = 16;
      if ( *a7 < 0x10 )
        goto LABEL_12;
      if ( a3 >= 2 && (a3 & 1) == 0 )
      {
        *((_WORD *)a2 + ((unsigned __int64)a3 >> 1) - 1) = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)a2);
        v14 = RtlGUIDFromString(&DestinationString, Guid);
        if ( v14 < 0 )
          goto LABEL_47;
LABEL_78:
        v13 = Size;
        goto LABEL_15;
      }
LABEL_42:
      BiLogMessage(4, L"String not multiple of WCHAR. Length %lu DataType: %lu");
      return (unsigned int)-1073741788;
    case 4:
      if ( a3 >= 2 && (a3 & 1) == 0 )
      {
        v19 = Guid;
        v14 = 0;
        *((_WORD *)a2 + ((unsigned __int64)a3 >> 1) - 1) = 0;
        if ( *(_WORD *)a2 )
        {
          do
          {
            if ( v8 >= v9 )
              break;
            v13 += 16;
            LODWORD(Size) = v13;
            if ( v13 <= *v7 )
            {
              RtlInitUnicodeString(&DestinationString, v11);
              v14 = RtlGUIDFromString(&DestinationString, v19);
              if ( v14 < 0 )
                goto LABEL_47;
              v13 = Size;
              ++v19;
            }
            v20 = -1;
            do
              ++v20;
            while ( v11[v20] );
            v8 += 2 * v20 + 2;
            v11 += (unsigned int)(v20 + 1);
          }
          while ( *v11 );
        }
        if ( v13 <= *v7 )
          goto LABEL_48;
        goto LABEL_12;
      }
      goto LABEL_42;
    case 5:
      v13 = 8;
      if ( a3 <= 8 )
      {
        if ( *a7 < 8 )
          goto LABEL_12;
        v15 = Guid;
        *(_QWORD *)&Guid->Data1 = 0;
        goto LABEL_14;
      }
      v17 = 8;
      v18 = L"Exceeded length for BCD element. Length %lu Expected: %lu DataType: %lu";
LABEL_27:
      BiLogMessage(4, v18, a3, v17, a4);
      return (unsigned int)-1073741788;
    case 6:
      if ( a3 != 1 )
      {
        BiLogMessage(4, L"Unexpected length for BCD element. Length %lu Expected: %lu DataType: %lu", a3, 1, a4);
        return (unsigned int)-1073741788;
      }
      v13 = 2;
      if ( *a7 < 2 )
        goto LABEL_12;
      v16 = Guid;
      BYTE1(Guid->Data1) = 0;
      LOBYTE(v16->Data1) = *(_BYTE *)a2 != 0;
      goto LABEL_15;
    case 7:
      if ( !a3 || (a3 & 7) != 0 )
        goto LABEL_9;
      v13 = a3;
      if ( *a7 < a3 )
        goto LABEL_12;
LABEL_13:
      v15 = Guid;
LABEL_14:
      memcpy_0(v15, a2, a3);
      goto LABEL_15;
  }
  if ( a3 )
  {
    v13 = a3;
    if ( a3 > *a7 )
    {
LABEL_12:
      v14 = -1073741789;
      goto LABEL_48;
    }
    goto LABEL_13;
  }
LABEL_9:
  BiLogMessage(4, L"Unexpected length for BCD element. Length %lu DataType: %lu");
  return (unsigned int)-1073741788;
}

```

## disassembly

```asm
0x140019544  push    rbp
0x140019546  push    rbx
0x140019547  push    rsi
0x140019548  push    rdi
0x140019549  push    r12
0x14001954b  push    r13
0x14001954d  push    r14
0x14001954f  push    r15
0x140019551  mov     rbp, rsp
0x140019554  sub     rsp, 68h
0x140019558  mov     r15, [rbp+arg_30]
0x14001955c  xor     r13d, r13d
0x14001955f  mov     eax, r9d
0x140019562  mov     edi, r8d
0x140019565  shr     eax, 18h
0x140019568  xorps   xmm0, xmm0
0x14001956b  and     eax, 0Fh
0x14001956e  mov     [rbp+P], r13
0x140019572  mov     dword ptr [rbp+Size], r13d
0x140019576  mov     r10d, r9d
0x140019579  mov     [rbp+var_28], r13
0x14001957d  mov     r14, rdx
0x140019580  mov     [rbp+var_38], r13d
0x140019584  mov     r12, rcx
0x140019587  mov     esi, r13d
0x14001958a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001958e  sub     eax, 1
0x140019591  jz      loc_140019816
0x140019597  sub     eax, 1
0x14001959a  jz      loc_1400197BE
0x1400195a0  sub     eax, 1
0x1400195a3  jz      loc_140019751
0x1400195a9  sub     eax, 1
0x1400195ac  jz      loc_1400196A3
0x1400195b2  sub     eax, 1
0x1400195b5  jz      loc_140019664
0x1400195bb  sub     eax, 1
0x1400195be  jz      short loc_140019623
0x1400195c0  cmp     eax, 1
0x1400195c3  jz      short loc_14001960A
0x1400195c5  test    r8d, r8d
0x1400195c8  jnz     short loc_1400195E5
0x1400195ca  lea     rdx, aUnexpectedLeng_0; "Unexpected length for BCD element. Leng"...
0x1400195d1  mov     ecx, 4
0x1400195d6  call    BiLogMessage
0x1400195db  mov     ebx, 0C0000024h
0x1400195e0  jmp     loc_1400197AB
0x1400195e5  mov     esi, edi
0x1400195e7  cmp     edi, [r15]
0x1400195ea  jbe     short loc_1400195F6
0x1400195ec  mov     ebx, 0C0000023h
0x1400195f1  jmp     loc_1400197A8
0x1400195f6  mov     rcx, [rbp+Guid]; void *
0x1400195fa  mov     r8, rdi; Size
0x1400195fd  call    memcpy_0
0x140019602  mov     ebx, r13d
0x140019605  jmp     loc_1400197A8
0x14001960a  test    r8d, r8d
0x14001960d  jz      short loc_14001961E
0x14001960f  test    dil, 7
0x140019613  jnz     short loc_14001961E
0x140019615  mov     esi, edi
0x140019617  cmp     [r15], edi
0x14001961a  jnb     short loc_1400195F6
0x14001961c  jmp     short loc_1400195EC
0x14001961e  mov     r8d, edi
0x140019621  jmp     short loc_1400195CA
0x140019623  mov     ebx, 1
0x140019628  cmp     edi, ebx
0x14001962a  jz      short loc_140019648
0x14001962c  mov     r9d, ebx
0x14001962f  mov     dword ptr [rsp+68h+var_48], r10d
0x140019634  mov     r8d, edi
0x140019637  lea     rdx, aUnexpectedLeng; "Unexpected length for BCD element. Leng"...
0x14001963e  lea     ecx, [rbx+3]
0x140019641  call    BiLogMessage
0x140019646  jmp     short loc_1400195DB
0x140019648  mov     esi, 2
0x14001964d  cmp     [r15], esi
0x140019650  jb      short loc_1400195EC
0x140019652  mov     rcx, [rbp+Guid]
0x140019656  mov     [rcx+1], r13b
0x14001965a  cmp     [rdx], r13b
0x14001965d  setnz   al
0x140019660  mov     [rcx], al
0x140019662  jmp     short loc_140019602
0x140019664  mov     esi, 8
0x140019669  cmp     edi, esi
0x14001966b  jbe     short loc_14001968E
0x14001966d  mov     r9d, esi
0x140019670  lea     rdx, aExceededLength; "Exceeded length for BCD element. Length"...
0x140019677  mov     r8d, edi
0x14001967a  mov     dword ptr [rsp+68h+var_48], r10d
0x14001967f  mov     ecx, 4
0x140019684  call    BiLogMessage
0x140019689  jmp     loc_1400195DB
0x14001968e  cmp     [r15], esi
0x140019691  jb      loc_1400195EC
0x140019697  mov     rcx, [rbp+Guid]
0x14001969b  mov     [rcx], r13
0x14001969e  jmp     loc_1400195FA
0x1400196a3  cmp     edi, 2
0x1400196a6  jb      loc_140019742
0x1400196ac  mov     ebx, 1
0x1400196b1  test    bl, dil
0x1400196b4  jnz     loc_140019742
0x1400196ba  mov     r12, [rbp+Guid]
0x1400196be  xor     edx, edx
0x1400196c0  mov     rcx, rdi
0x1400196c3  mov     ebx, edx
0x1400196c5  shr     rcx, 1
0x1400196c8  mov     [r14+rcx*2-2], dx
0x1400196ce  cmp     [r14], dx
0x1400196d2  jz      short loc_140019738
0x1400196d4  cmp     r13d, edi
0x1400196d7  jnb     short loc_140019734
0x1400196d9  add     esi, 10h
0x1400196dc  mov     dword ptr [rbp+Size], esi
0x1400196df  cmp     esi, [r15]
0x1400196e2  ja      short loc_140019711
0x1400196e4  mov     rdx, r14; SourceString
0x1400196e7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400196eb  call    cs:__imp_RtlInitUnicodeString
0x1400196f1  mov     rdx, r12; Guid
0x1400196f4  lea     rcx, [rbp+DestinationString]; GuidString
0x1400196f8  call    cs:__imp_RtlGUIDFromString
0x1400196fe  xor     edx, edx
0x140019700  mov     ebx, eax
0x140019702  test    eax, eax
0x140019704  js      loc_14001979D
0x14001970a  mov     esi, dword ptr [rbp+Size]
0x14001970d  add     r12, 10h
0x140019711  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019715  inc     rax
0x140019718  cmp     [r14+rax*2], dx
0x14001971d  jnz     short loc_140019715
0x14001971f  lea     r13d, [r13+rax*2+0]
0x140019724  add     r13d, 2
0x140019728  inc     eax
0x14001972a  lea     r14, [r14+rax*2]
0x14001972e  cmp     [r14], dx
0x140019732  jnz     short loc_1400196D4
0x140019734  test    ebx, ebx
0x140019736  js      short loc_1400197A0
0x140019738  cmp     esi, [r15]
0x14001973b  jbe     short loc_1400197A8
0x14001973d  jmp     loc_1400195EC
0x140019742  mov     r8d, edi
0x140019745  lea     rdx, aStringNotMulti; "String not multiple of WCHAR. Length %l"...
0x14001974c  jmp     loc_1400195D1
0x140019751  mov     esi, 10h
0x140019756  mov     dword ptr [rbp+Size], esi
0x140019759  cmp     [r15], esi
0x14001975c  jb      loc_1400195EC
0x140019762  cmp     edi, 2
0x140019765  jb      short loc_140019742
0x140019767  lea     ebx, [rsi-0Fh]
0x14001976a  test    bl, dil
0x14001976d  jnz     short loc_140019742
0x14001976f  mov     rcx, rdi
0x140019772  shr     rcx, 1
0x140019775  mov     [rdx+rcx*2-2], r13w
0x14001977b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001977f  call    cs:__imp_RtlInitUnicodeString
0x140019785  mov     rdx, [rbp+Guid]; Guid
0x140019789  lea     rcx, [rbp+DestinationString]; GuidString
0x14001978d  call    cs:__imp_RtlGUIDFromString
0x140019793  mov     ebx, eax
0x140019795  test    eax, eax
0x140019797  jns     loc_140019981
0x14001979d  mov     esi, dword ptr [rbp+Size]
0x1400197a0  cmp     ebx, 0C0000023h
0x1400197a6  jnz     short loc_1400197AB
0x1400197a8  mov     [r15], esi
0x1400197ab  mov     eax, ebx
0x1400197ad  add     rsp, 68h
0x1400197b1  pop     r15
0x1400197b3  pop     r14
0x1400197b5  pop     r13
0x1400197b7  pop     r12
0x1400197b9  pop     rdi
0x1400197ba  pop     rsi
0x1400197bb  pop     rbx
0x1400197bc  pop     rbp
0x1400197bd  retn
0x1400197be  test    r8d, r8d
0x1400197c1  jz      loc_140019742
0x1400197c7  mov     ebx, 1
0x1400197cc  test    bl, dil
0x1400197cf  jnz     loc_140019742
0x1400197d5  mov     esi, edi
0x1400197d7  mov     r12, rdi
0x1400197da  cmp     [rdi+rdx-2], r13w
0x1400197e0  jz      short loc_1400197E9
0x1400197e2  add     edi, 2
0x1400197e5  mov     esi, edi
0x1400197e7  jmp     short loc_1400197EC
0x1400197e9  mov     bl, r13b
0x1400197ec  cmp     edi, [r15]
0x1400197ef  ja      loc_1400195EC
0x1400197f5  mov     rdi, [rbp+Guid]
0x1400197f9  mov     r8, r12; Size
0x1400197fc  mov     rcx, rdi; void *
0x1400197ff  call    memcpy_0
0x140019804  test    bl, bl
0x140019806  jz      loc_140019602
0x14001980c  mov     [r12+rdi], r13w
0x140019811  jmp     loc_140019602
0x140019816  mov     r9d, 1Ch
0x14001981c  cmp     edi, r9d
0x14001981f  jnb     short loc_14001982D
0x140019821  lea     rdx, aInsufficientLe; "Insufficient length for BCD element. Le"...
0x140019828  jmp     loc_140019677
0x14001982d  lea     rcx, [rdx+10h]; Src
0x140019831  mov     r9d, [rcx+8]
0x140019835  add     r9, 10h
0x140019839  cmp     r9, rdi
0x14001983c  jz      short loc_14001984A
0x14001983e  lea     rdx, aUnexpectedLeng; "Unexpected length for BCD element. Leng"...
0x140019845  jmp     loc_140019677
0x14001984a  mov     edi, [rbp+arg_20]
0x14001984d  mov     ebx, 1
0x140019852  test    bl, dil
0x140019855  jz      short loc_140019866
0x140019857  lea     r8, [rbp+Size]
0x14001985b  lea     rdx, [rbp+P]
0x14001985f  call    BiConvertBootEnvironmentDeviceToQualifiedPartition
0x140019864  jmp     short loc_140019893
0x140019866  test    dil, 2
0x14001986a  jz      short loc_14001987B
0x14001986c  lea     r8, [rbp+Size]
0x140019870  lea     rdx, [rbp+P]
0x140019874  call    BiConvertBootEnvironmentDeviceToUnknown
0x140019879  jmp     short loc_140019893
0x14001987b  lea     rax, [rbp+Size]
0x14001987f  mov     r8d, edi
0x140019882  lea     r9, [rbp+P]
0x140019886  mov     [rsp+68h+var_48], rax
0x14001988b  mov     edx, r10d
0x14001988e  call    BiConvertBootEnvironmentDeviceToNt
0x140019893  mov     ebx, eax
0x140019895  test    eax, eax
0x140019897  js      loc_14001979D
0x14001989d  mov     rcx, [rbp+P]
0x1400198a1  mov     esi, 8
0x1400198a6  cmp     [rcx], esi
0x1400198a8  jnz     short loc_14001991E
0x1400198aa  bt      edi, 8
0x1400198ae  jnb     short loc_1400198F1
0x1400198b0  lea     r9, [rbp+var_38]
0x1400198b4  mov     rdx, r12
0x1400198b7  lea     r8, [rbp+var_28]
0x1400198bb  call    BiResolveLocate
0x1400198c0  test    eax, eax
0x1400198c2  js      short loc_14001991A
0x1400198c4  mov     rcx, gs:60h
0x1400198cd  xor     edx, edx; Flags
0x1400198cf  mov     r8, [rbp+P]; P
0x1400198d3  mov     rcx, [rcx+30h]; HeapHandle
0x1400198d7  call    cs:__imp_RtlFreeHeap
0x1400198dd  mov     rcx, [rbp+var_28]
0x1400198e1  mov     eax, [rbp+var_38]
0x1400198e4  mov     [rbp+P], rcx
0x1400198e8  mov     dword ptr [rbp+Size], eax
0x1400198eb  mov     [rbp+var_28], r13
0x1400198ef  jmp     short loc_14001991E
0x1400198f1  mov     rdx, rcx
0x1400198f4  mov     rcx, r12
0x1400198f7  call    BiResolveLocateDevice
0x1400198fc  test    eax, eax
0x1400198fe  js      short loc_14001991A
0x140019900  mov     rcx, [rbp+P]; void *
0x140019904  mov     eax, dword ptr [rbp+Size]
0x140019907  mov     edx, [rcx+18h]
0x14001990a  sub     eax, edx
0x14001990c  add     rdx, rcx; Src
0x14001990f  mov     r8d, eax; Size
0x140019912  mov     dword ptr [rbp+Size], eax
0x140019915  call    memmove_0
0x14001991a  mov     rcx, [rbp+P]
0x14001991e  mov     eax, [r15]
0x140019921  cmp     dword ptr [rbp+Size], eax
0x140019924  jbe     short loc_14001994C
0x140019926  mov     rcx, gs:60h
0x14001992f  xor     edx, edx; Flags
0x140019931  mov     r8, [rbp+P]; P
0x140019935  mov     ebx, 0C0000023h
0x14001993a  mov     rcx, [rcx+30h]; HeapHandle
0x14001993e  call    cs:__imp_RtlFreeHeap
0x140019944  mov     esi, dword ptr [rbp+Size]
0x140019947  jmp     loc_1400197A8
0x14001994c  mov     rbx, [rbp+Guid]
0x140019950  mov     rdx, rcx; Src
0x140019953  mov     r8d, dword ptr [rbp+Size]; Size
0x140019957  mov     rcx, rbx; void *
0x14001995a  call    memcpy_0
0x14001995f  movups  xmm0, xmmword ptr [r14]
0x140019963  xor     edx, edx; Flags
0x140019965  movdqu  xmmword ptr [rbx+4], xmm0
0x14001996a  mov     rcx, gs:60h
  ... truncated ...
```
