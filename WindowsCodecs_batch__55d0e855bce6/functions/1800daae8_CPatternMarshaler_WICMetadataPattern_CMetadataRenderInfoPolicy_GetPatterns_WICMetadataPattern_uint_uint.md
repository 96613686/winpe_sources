# CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(WICMetadataPattern * *,uint *,uint *)

- ea: `0x1800daae8`
- end: `0x1800dabe8`
- name: `?GetPatterns@?$CPatternMarshaler@UWICMetadataPattern@@VCMetadataRenderInfoPolicy@@@@AEAAJPEAPEAUWICMetadataPattern@@PEAI1@Z`
- size: `256`
- prototype: `__int64 __fastcall(CMetadataRenderInfoPolicy *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800da788`

## callees

- `0x1800bd9d4`
- `0x1800daae8`
- `0x1800dabf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dab4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dab4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dabcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dabcc`

## pseudocode

```c
__int64 __fastcall CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(
        CMetadataRenderInfoPolicy *this,
        struct WICMetadataPattern **a2,
        unsigned int *a3,
        _DWORD *a4)
{
  int Patterns; // eax
  unsigned int v9; // ebx
  struct WICMetadataPattern *v10; // rdi
  int v11; // ecx
  int v12; // eax
  unsigned int v14[18]; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(cb) = 0;
  v14[0] = 0;
  Patterns = CMetadataRenderInfoPolicy::GetPatterns(this, 0, 0, 0, (unsigned int *)&cb);
  v9 = Patterns;
  if ( Patterns < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(Patterns);
    goto LABEL_13;
  }
  v10 = (struct WICMetadataPattern *)CoTaskMemAlloc((unsigned int)cb);
  if ( v10 )
  {
    v12 = CMetadataRenderInfoPolicy::GetPatterns(this, cb, v10, v14, (unsigned int *)&cb);
    v9 = v12;
    if ( v12 >= 0 )
    {
      *a3 = v14[0];
      *a4 = cb;
      *a2 = v10;
LABEL_13:
      v10 = 0;
      goto LABEL_14;
    }
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_14;
    v11 = v12;
    goto LABEL_7;
  }
  v9 = -2147024882;
  if ( (_DWORD)g_doStackCaptures )
  {
    v11 = -2147024882;
LABEL_7:
    DoStackCapture(v11);
  }
LABEL_14:
  CoTaskMemFree(v10);
  return v9;
}

```

## disassembly

```asm
0x1800daae8  mov     rax, rsp
0x1800daaeb  push    rbx
0x1800daaec  push    rbp
0x1800daaed  push    rsi
0x1800daaee  push    rdi
0x1800daaef  push    r14
0x1800daaf1  push    r15
0x1800daaf3  sub     rsp, 48h
0x1800daaf7  mov     dword ptr [rax+8], 0
0x1800daafe  mov     r14, r9
0x1800dab01  mov     dword ptr [rax-48h], 0
0x1800dab08  lea     rax, [rax+8]
0x1800dab0c  mov     r15, r8
0x1800dab0f  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800dab14  mov     rbp, rdx
0x1800dab17  xor     r9d, r9d; unsigned int *
0x1800dab1a  xor     r8d, r8d; struct WICMetadataPattern *
0x1800dab1d  xor     edx, edx; unsigned int
0x1800dab1f  mov     rsi, rcx
0x1800dab22  call    ?GetPatterns@CMetadataRenderInfoPolicy@@QEAAJIPEAUWICMetadataPattern@@PEAI1@Z; CMetadataRenderInfoPolicy::GetPatterns(uint,WICMetadataPattern *,uint *,uint *)
0x1800dab27  mov     ebx, eax
0x1800dab29  test    eax, eax
0x1800dab2b  jns     short loc_1800DAB46
0x1800dab2d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800dab34  jz      loc_1800DABC7
0x1800dab3a  mov     ecx, eax; int
0x1800dab3c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800dab41  jmp     loc_1800DABC7
0x1800dab46  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x1800dab4d  call    cs:__imp_CoTaskMemAlloc
0x1800dab54  nop     dword ptr [rax+rax+00h]
0x1800dab59  mov     rdi, rax
0x1800dab5c  test    rax, rax
0x1800dab5f  jnz     short loc_1800DAB77
0x1800dab61  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800dab67  mov     ebx, 8007000Eh
0x1800dab6c  jz      short loc_1800DABC9
0x1800dab6e  mov     ecx, ebx; int
0x1800dab70  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800dab75  jmp     short loc_1800DABC9
0x1800dab77  mov     edx, dword ptr [rsp+78h+cb]; unsigned int
0x1800dab7e  lea     rax, [rsp+78h+cb]
0x1800dab86  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800dab8b  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800dab90  mov     r8, rdi; struct WICMetadataPattern *
0x1800dab93  mov     rcx, rsi; this
0x1800dab96  call    ?GetPatterns@CMetadataRenderInfoPolicy@@QEAAJIPEAUWICMetadataPattern@@PEAI1@Z; CMetadataRenderInfoPolicy::GetPatterns(uint,WICMetadataPattern *,uint *,uint *)
0x1800dab9b  mov     ebx, eax
0x1800dab9d  test    eax, eax
0x1800dab9f  jns     short loc_1800DABB2
0x1800daba1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800daba8  jz      short loc_1800DABAE
0x1800dabaa  mov     ecx, eax
0x1800dabac  jmp     short loc_1800DAB70
0x1800dabae  test    eax, eax
0x1800dabb0  js      short loc_1800DABC9
0x1800dabb2  mov     ecx, [rsp+78h+var_48]
0x1800dabb6  mov     [r15], ecx
0x1800dabb9  mov     ecx, dword ptr [rsp+78h+cb]
0x1800dabc0  mov     [r14], ecx
0x1800dabc3  mov     [rbp+0], rdi
0x1800dabc7  xor     edi, edi
0x1800dabc9  mov     rcx, rdi; pv
0x1800dabcc  call    cs:__imp_CoTaskMemFree
0x1800dabd3  nop     dword ptr [rax+rax+00h]
0x1800dabd8  mov     eax, ebx
0x1800dabda  add     rsp, 48h
0x1800dabde  pop     r15
0x1800dabe0  pop     r14
0x1800dabe2  pop     rdi
0x1800dabe3  pop     rsi
0x1800dabe4  pop     rbp
0x1800dabe5  pop     rbx
0x1800dabe6  retn
```
