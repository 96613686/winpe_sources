# StructuredQuery1::QueryParser::GetParsedConditions(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,ulong,_GUID const &,void * *,wchar_t * *,wchar_t * *,ulong *,_GUID const &,void * *)

- ea: `0x180055a30`
- end: `0x180055be6`
- name: `?GetParsedConditions@QueryParser@StructuredQuery1@@UEAAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@KAEBU_GUID@@PEAPEAXPEAPEA_W4PEAK23@Z`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013174`
- `0x180052278`
- `0x1800523f8`
- `0x180055a30`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055b83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055b9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055b83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055b9b`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::GetParsedConditions(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, struct _GUID *, void **),
        unsigned int a3,
        unsigned int a4,
        struct _GUID *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        struct _GUID *a10,
        _QWORD *a11)
{
  _DWORD *v11; // r15
  unsigned __int64 v14; // rdi
  StructuredQuery1::Solution *v15; // rax
  __int64 v16; // rbx
  int MostRecentParsedConditionRecursively; // ebp
  FILETIME *v18; // rcx
  int ParsedConditionsRecursively; // eax
  _QWORD v21[11]; // [rsp+60h] [rbp-58h] BYREF

  v11 = a9;
  if ( a9 )
    *a9 = 0;
  v14 = (unsigned __int64)a11;
  if ( a11 )
    *a11 = 0;
  v15 = (StructuredQuery1::Solution *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v15 || (v16 = StructuredQuery1::Solution::Solution(v15)) == 0 )
    return (unsigned int)-2147024882;
  v21[0] = 0;
  if ( (a3 & 2) == 0 )
  {
    v18 = 0;
LABEL_11:
    LODWORD(a11) = 0;
    ParsedConditionsRecursively = StructuredQuery1::GetParsedConditionsRecursively(
                                    a2,
                                    a3,
                                    a4,
                                    a5,
                                    a6,
                                    a7,
                                    a8,
                                    (unsigned int *)&a11,
                                    v18,
                                    a10,
                                    v14,
                                    v16,
                                    v21[0]);
    LODWORD(v14) = (_DWORD)a11;
    MostRecentParsedConditionRecursively = ParsedConditionsRecursively;
    if ( ParsedConditionsRecursively < 0 && (_DWORD)a11 )
    {
      do
      {
        v14 = (unsigned int)(v14 - 1);
        if ( a6 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a6 + 8 * v14) + 16LL))(*(_QWORD *)(a6 + 8 * v14));
          *(_QWORD *)(a6 + 8 * v14) = 0;
        }
        if ( a7 )
        {
          CoTaskMemFree(*(LPVOID *)(a7 + 8LL * (unsigned int)v14));
          *(_QWORD *)(a7 + 8 * v14) = 0;
        }
        if ( a8 )
        {
          CoTaskMemFree(*(LPVOID *)(a8 + 8LL * (unsigned int)v14));
          *(_QWORD *)(a8 + 8 * v14) = 0;
        }
      }
      while ( (_DWORD)v14 );
      v11 = a9;
    }
    if ( v11 )
      *v11 = v14;
    goto LABEL_23;
  }
  MostRecentParsedConditionRecursively = StructuredQuery1::GetMostRecentParsedConditionRecursively(a2, a3, v21);
  if ( MostRecentParsedConditionRecursively >= 0 )
  {
    v18 = (FILETIME *)v21;
    goto LABEL_11;
  }
LABEL_23:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)MostRecentParsedConditionRecursively;
}

```

## disassembly

```asm
0x180055a30  mov     [rsp+arg_18], r9d
0x180055a35  push    rbx
0x180055a36  push    rbp
0x180055a37  push    rsi
0x180055a38  push    rdi
0x180055a39  push    r12
0x180055a3b  push    r13
0x180055a3d  push    r14
0x180055a3f  push    r15
0x180055a41  sub     rsp, 78h
0x180055a45  mov     r15, [rsp+0B8h+arg_40]
0x180055a4d  xor     r12d, r12d
0x180055a50  mov     esi, r8d
0x180055a53  mov     r14, rdx
0x180055a56  test    r15, r15
0x180055a59  jz      short loc_180055A5E
0x180055a5b  mov     [r15], r12d
0x180055a5e  mov     rdi, [rsp+0B8h+arg_50]
0x180055a66  test    rdi, rdi
0x180055a69  jz      short loc_180055A6E
0x180055a6b  mov     [rdi], r12
0x180055a6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180055a75  mov     ecx, 120h; unsigned __int64
0x180055a7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180055a7f  test    rax, rax
0x180055a82  jz      loc_180055BCE
0x180055a88  mov     rcx, rax; this
0x180055a8b  call    ??0Solution@StructuredQuery1@@AEAA@XZ; StructuredQuery1::Solution::Solution(void)
0x180055a90  mov     rbx, rax
0x180055a93  test    rax, rax
0x180055a96  jz      loc_180055BCE
0x180055a9c  mov     [rsp+0B8h+var_58], r12
0x180055aa1  test    sil, 2
0x180055aa5  jz      short loc_180055AC7
0x180055aa7  lea     r8, [rsp+0B8h+var_58]
0x180055aac  mov     edx, esi
0x180055aae  mov     rcx, r14
0x180055ab1  call    ?GetMostRecentParsedConditionRecursively@StructuredQuery1@@YAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@PEAU_FILETIME@@@Z; StructuredQuery1::GetMostRecentParsedConditionRecursively(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,_FILETIME *)
0x180055ab6  mov     ebp, eax
0x180055ab8  test    eax, eax
0x180055aba  js      loc_180055BBD
0x180055ac0  lea     rcx, [rsp+0B8h+var_58]
0x180055ac5  jmp     short loc_180055ACA
0x180055ac7  mov     rcx, r12
0x180055aca  mov     rax, [rsp+0B8h+arg_48]
0x180055ad2  mov     edx, esi
0x180055ad4  mov     r13, [rsp+0B8h+arg_30]
0x180055adc  mov     r9, [rsp+0B8h+arg_20]
0x180055ae4  mov     r8d, [rsp+0B8h+arg_18]
0x180055aec  mov     [rsp+0B8h+var_60], rbx
0x180055af1  mov     [rsp+0B8h+var_68], rdi
0x180055af6  mov     [rsp+0B8h+var_70], rax
0x180055afb  lea     rax, [rsp+0B8h+arg_50]
0x180055b03  mov     [rsp+0B8h+var_78], rcx
0x180055b08  mov     rcx, r14
0x180055b0b  mov     [rsp+0B8h+var_80], rax
0x180055b10  mov     rax, [rsp+0B8h+arg_28]
0x180055b18  mov     dword ptr [rsp+0B8h+arg_50], r12d
0x180055b20  mov     r12, [rsp+0B8h+arg_38]
0x180055b28  mov     [rsp+0B8h+var_88], r12
0x180055b2d  mov     [rsp+0B8h+var_90], r13
0x180055b32  mov     [rsp+0B8h+var_98], rax
0x180055b37  call    ?GetParsedConditionsRecursively@StructuredQuery1@@YAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@KAEBU_GUID@@PEAPEAXPEAPEA_W4PEAKPEBU_FILETIME@@23PEAVSolution@1@@Z; StructuredQuery1::GetParsedConditionsRecursively(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,ulong,_GUID const &,void * *,wchar_t * *,wchar_t * *,ulong *,_FILETIME const *,_GUID const &,void * *,StructuredQuery1::Solution *)
0x180055b3c  mov     edi, dword ptr [rsp+0B8h+arg_50]
0x180055b43  mov     ebp, eax
0x180055b45  test    eax, eax
0x180055b47  jns     short loc_180055BB5
0x180055b49  test    edi, edi
0x180055b4b  jz      short loc_180055BB5
0x180055b4d  mov     r15, [rsp+0B8h+arg_28]
0x180055b55  dec     edi
0x180055b57  mov     esi, edi
0x180055b59  test    r15, r15
0x180055b5c  jz      short loc_180055B76
0x180055b5e  mov     rcx, [r15+rdi*8]
0x180055b62  mov     rax, [rcx]
0x180055b65  mov     rax, [rax+10h]
0x180055b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b6e  mov     qword ptr [r15+rdi*8], 0
0x180055b76  mov     r14, rsi
0x180055b79  test    r13, r13
0x180055b7c  jz      short loc_180055B92
0x180055b7e  mov     rcx, [r13+rsi*8+0]; pv
0x180055b83  call    cs:__imp_CoTaskMemFree
0x180055b89  mov     qword ptr [r13+rdi*8+0], 0
0x180055b92  test    r12, r12
0x180055b95  jz      short loc_180055BA9
0x180055b97  mov     rcx, [r12+r14*8]; pv
0x180055b9b  call    cs:__imp_CoTaskMemFree
0x180055ba1  mov     qword ptr [r12+rdi*8], 0
0x180055ba9  test    edi, edi
0x180055bab  jnz     short loc_180055B55
0x180055bad  mov     r15, [rsp+0B8h+arg_40]
0x180055bb5  test    r15, r15
0x180055bb8  jz      short loc_180055BBD
0x180055bba  mov     [r15], edi
0x180055bbd  mov     rax, [rbx]
0x180055bc0  mov     rcx, rbx
0x180055bc3  mov     rax, [rax+10h]
0x180055bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bcc  jmp     short loc_180055BD3
0x180055bce  mov     ebp, 8007000Eh
0x180055bd3  mov     eax, ebp
0x180055bd5  add     rsp, 78h
0x180055bd9  pop     r15
0x180055bdb  pop     r14
0x180055bdd  pop     r13
0x180055bdf  pop     r12
0x180055be1  pop     rdi
0x180055be2  pop     rsi
0x180055be3  pop     rbp
0x180055be4  pop     rbx
0x180055be5  retn
```
