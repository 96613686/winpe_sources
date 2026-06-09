# EnsureStorageIsAppContainerCompliant

- ea: `0x180007000`
- end: `0x1800071aa`
- name: `EnsureStorageIsAppContainerCompliant`
- size: `426`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008550`
- `0x180009790`

## callees

- `0x180002ab8`
- `0x180007000`
- `0x180010010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007068`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007107`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007068`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007107`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800070bc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007158`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800070bc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007158`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageSettings` at `0x1800070a3`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageSettings` at `0x1800070a3`
- `ext-ms-win-storage-sense-l1-1-0!SetStorageSettings` at `0x18000713f`
- `ext-ms-win-storage-sense-l1-1-0!SetStorageSettings` at `0x18000713f`

## string_xrefs

- `0x18000705c`: `EnsureStorageIsAppContainerCompliant`
- `0x1800070b3`: `EnsureStorageIsAppContainerCompliant`
- `0x1800070fb`: `EnsureStorageIsAppContainerCompliant`
- `0x18000714f`: `EnsureStorageIsAppContainerCompliant`

## pseudocode

```c
__int64 __fastcall EnsureStorageIsAppContainerCompliant(unsigned int *a1)
{
  unsigned int v2; // edi
  unsigned int v3; // ebx
  int StorageSettings; // eax
  int v5; // eax
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+38h] [rbp+10h]

  v2 = 0;
  v7 = 0;
  if ( (a1[275] & 2) == 0 )
  {
    v3 = 0;
    v8 = 0;
    if ( qword_1800184A8 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, 2);
      v8 = v3;
    }
    if ( (unsigned __int8)IsSelectStorageVolumeExPresent() )
    {
      StorageSettings = GetStorageSettings(a1[133], *a1, 2, &v7);
      if ( StorageSettings >= 0 )
      {
        v7 |= 0x10010u;
        if ( (unsigned __int8)IsSelectStorageVolumeExPresent() )
        {
          v5 = SetStorageSettings(a1[133], *a1, 2, v7);
          if ( v5 >= 0 )
          {
            if ( qword_1800184A8 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v3);
          }
          else
          {
            v2 = ZTraceReportPropagationNoThis(v5, "EnsureStorageIsAppContainerCompliant", 520);
            if ( qword_1800184A8 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v3);
          }
        }
        else
        {
          v2 = ZTraceReportOriginationNoThis(-2147024769, "EnsureStorageIsAppContainerCompliant", 519);
          if ( qword_1800184A8 )
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v3);
        }
      }
      else
      {
        v2 = ZTraceReportPropagationNoThis(StorageSettings, "EnsureStorageIsAppContainerCompliant", 516);
        if ( qword_1800184A8 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v3);
      }
    }
    else
    {
      v2 = ZTraceReportOriginationNoThis(-2147024769, "EnsureStorageIsAppContainerCompliant", 515);
      if ( qword_1800184A8 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v3);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180007000  mov     [rsp+arg_10], rbx
0x180007005  mov     [rsp+arg_18], rsi
0x18000700a  push    rdi
0x18000700b  sub     rsp, 20h
0x18000700f  mov     rsi, rcx
0x180007012  xor     edi, edi
0x180007014  mov     [rsp+28h+arg_0], edi
0x180007018  mov     eax, [rcx+44Ch]
0x18000701e  test    al, 2
0x180007020  jnz     loc_180007198
0x180007026  xor     ebx, ebx
0x180007028  mov     [rsp+28h+arg_8], ebx
0x18000702c  mov     rcx, cs:qword_1800184A8
0x180007033  test    rcx, rcx
0x180007036  jz      short loc_18000704D
0x180007038  mov     rax, [rcx]
0x18000703b  lea     edx, [rdi+2]
0x18000703e  mov     rax, [rax+18h]
0x180007042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007047  mov     ebx, eax
0x180007049  mov     [rsp+28h+arg_8], eax
0x18000704d  call    IsSelectStorageVolumeExPresent
0x180007052  test    al, al
0x180007054  jnz     short loc_180007090
0x180007056  mov     r8d, 203h
0x18000705c  lea     rdx, aEnsurestoragei; "EnsureStorageIsAppContainerCompliant"
0x180007063  mov     ecx, 8007007Fh
0x180007068  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000706e  mov     edi, eax
0x180007070  mov     rcx, cs:qword_1800184A8
0x180007077  test    rcx, rcx
0x18000707a  jz      short loc_18000708B
0x18000707c  mov     rdx, [rcx]
0x18000707f  mov     rax, [rdx+18h]
0x180007083  mov     edx, ebx
0x180007085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000708a  nop
0x18000708b  jmp     loc_180007198
0x180007090  lea     r9, [rsp+28h+arg_0]
0x180007095  mov     r8d, 2
0x18000709b  mov     edx, [rsi]
0x18000709d  mov     ecx, [rsi+214h]
0x1800070a3  call    cs:__imp_GetStorageSettings
0x1800070a9  test    eax, eax
0x1800070ab  jns     short loc_1800070E4
0x1800070ad  mov     r8d, 204h
0x1800070b3  lea     rdx, aEnsurestoragei; "EnsureStorageIsAppContainerCompliant"
0x1800070ba  mov     ecx, eax
0x1800070bc  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800070c2  mov     edi, eax
0x1800070c4  mov     rcx, cs:qword_1800184A8
0x1800070cb  test    rcx, rcx
0x1800070ce  jz      short loc_1800070DF
0x1800070d0  mov     rax, [rcx]
0x1800070d3  mov     edx, ebx
0x1800070d5  mov     rax, [rax+18h]
0x1800070d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070de  nop
0x1800070df  jmp     loc_180007198
0x1800070e4  or      [rsp+28h+arg_0], 10010h
0x1800070ec  call    IsSelectStorageVolumeExPresent
0x1800070f1  test    al, al
0x1800070f3  jnz     short loc_18000712C
0x1800070f5  mov     r8d, 207h
0x1800070fb  lea     rdx, aEnsurestoragei; "EnsureStorageIsAppContainerCompliant"
0x180007102  mov     ecx, 8007007Fh
0x180007107  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000710d  mov     edi, eax
0x18000710f  mov     rcx, cs:qword_1800184A8
0x180007116  test    rcx, rcx
0x180007119  jz      short loc_18000712A
0x18000711b  mov     rax, [rcx]
0x18000711e  mov     edx, ebx
0x180007120  mov     rax, [rax+18h]
0x180007124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007129  nop
0x18000712a  jmp     short loc_180007198
0x18000712c  mov     r9d, [rsp+28h+arg_0]
0x180007131  mov     r8d, 2
0x180007137  mov     edx, [rsi]
0x180007139  mov     ecx, [rsi+214h]
0x18000713f  call    cs:__imp_SetStorageSettings
0x180007145  test    eax, eax
0x180007147  jns     short loc_18000717D
0x180007149  mov     r8d, 208h
0x18000714f  lea     rdx, aEnsurestoragei; "EnsureStorageIsAppContainerCompliant"
0x180007156  mov     ecx, eax
0x180007158  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000715e  mov     edi, eax
0x180007160  mov     rcx, cs:qword_1800184A8
0x180007167  test    rcx, rcx
0x18000716a  jz      short loc_18000717B
0x18000716c  mov     rax, [rcx]
0x18000716f  mov     edx, ebx
0x180007171  mov     rax, [rax+18h]
0x180007175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717a  nop
0x18000717b  jmp     short loc_180007198
0x18000717d  mov     rcx, cs:qword_1800184A8
0x180007184  test    rcx, rcx
0x180007187  jz      short loc_180007198
0x180007189  mov     rax, [rcx]
0x18000718c  mov     edx, ebx
0x18000718e  mov     rax, [rax+18h]
0x180007192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007197  nop
0x180007198  mov     eax, edi
0x18000719a  mov     rbx, [rsp+28h+arg_10]
0x18000719f  mov     rsi, [rsp+28h+arg_18]
0x1800071a4  add     rsp, 20h
0x1800071a8  pop     rdi
0x1800071a9  retn
```
