# Projection::NamespaceProjection::GetDirectNamespaceChildren(void)

- ea: `0x18024e84c`
- end: `0x18024ea79`
- name: `?GetDirectNamespaceChildren@NamespaceProjection@Projection@@AEAAJXZ`
- size: `557`
- prototype: `__int64 __fastcall(Projection::NamespaceProjection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18024ea80`

## callees

- `0x18012a330`
- `0x180244950`
- `0x18024e15c`
- `0x18024e84c`
- `0x18024f514`
- `0x18035e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18024e934`
- `msvcrt!wcscpy_s` at `0x18024e934`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e955`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e975`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e9e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e9f8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024ea30`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024ea40`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e955`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e975`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e9e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e9f8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024ea30`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024ea40`

## pseudocode

```c
__int64 __fastcall Projection::NamespaceProjection::GetDirectNamespaceChildren(Projection::NamespaceProjection *this)
{
  int v2; // edi
  unsigned int v3; // esi
  int v4; // ebx
  wchar_t *v5; // r15
  __int64 v6; // rax
  rsize_t v7; // r12
  wchar_t *v8; // r13
  unsigned int i; // ebx
  void *v10; // rcx
  char *v11; // r14
  unsigned int v12; // esi
  unsigned int j; // ebx
  __int64 v14; // rdx
  __int64 result; // rax
  struct Js::RecyclableObject *v16; // r8
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-64h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-58h] BYREF
  LPVOID v21[2]; // [rsp+58h] [rbp-50h] BYREF
  _QWORD *v22; // [rsp+68h] [rbp-40h] BYREF
  char *(__fastcall *v23)(ArenaAllocator *__hidden, unsigned __int64); // [rsp+70h] [rbp-38h] BYREF
  int v24; // [rsp+78h] [rbp-30h]
  int v25; // [rsp+7Ch] [rbp-2Ch]

  v21[1] = (LPVOID)-2LL;
  try
  {
    RuntimeErrorWithScriptEnter = 0;
    v19 = 0;
    v18 = 0;
    pv = 0;
    v21[0] = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, LPVOID *, unsigned int *, LPVOID *, LPVOID *))(**(_QWORD **)(*((_QWORD *)this + 8) + 40LL) + 48LL))(
               *(_QWORD *)(*((_QWORD *)this + 8) + 40LL),
               *((_QWORD *)this + 3),
               &RuntimeErrorWithScriptEnter,
               &v19,
               &v18,
               &pv,
               v21);
  }
  catch ( Js::InternalErrorException )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::OutOfMemoryException )
  {
    RuntimeErrorWithScriptEnter = -2147024882;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::StackOverflowException )
  {
    RuntimeErrorWithScriptEnter = -2146828260;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::NotImplementedException )
  {
    RuntimeErrorWithScriptEnter = -2147467263;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::ScriptAbortException )
  {
    RuntimeErrorWithScriptEnter = -2147467260;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::JavascriptExceptionObject *v22 )
  {
    if ( *v22
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v22) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v16) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v16, 0);
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147024882;
    }
    return RuntimeErrorWithScriptEnter;
  }
  catch ( ... )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
    return RuntimeErrorWithScriptEnter;
  }
  v2 = result;
  if ( (int)result >= 0 )
  {
    v3 = 0;
    v4 = v25;
    while ( v3 < v18 )
    {
      v5 = (wchar_t *)*((_QWORD *)pv + v3);
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      v7 = v6 + 1;
      v23 = ArenaAllocator::Alloc;
      v24 = 0;
      v25 = v4;
      v8 = (wchar_t *)AllocateArray<ArenaAllocator,unsigned short,0>(
                        *(_QWORD *)(*((_QWORD *)this + 8) + 24LL),
                        (__int64)&v23,
                        v6 + 1);
      wcscpy_s(v8, v7, v5);
      *((_QWORD *)this + 4) = regex::ImmutableList<ProjectionModel::Property const *>::Prepend(
                                *((_QWORD *)this + 4),
                                v8,
                                *(_QWORD *)(*((_QWORD *)this + 8) + 24LL));
      CoTaskMemFree(v5);
      *((_QWORD *)pv + v3++) = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= RuntimeErrorWithScriptEnter )
      {
        *((_QWORD *)this + 4) = regex::ImmutableList<unsigned short const *>::SortCurrentList(*((_QWORD *)this + 4));
        CoTaskMemFree(v19);
        v19 = 0;
        CoTaskMemFree(v21[0]);
        return (unsigned int)v2;
      }
      v2 = Projection::NamespaceProjection::AddDirectChildTypesFromMetadata(
             this,
             *((struct IUnknown **)v19 + i),
             *((_DWORD *)v21[0] + i));
      if ( v2 < 0 )
        break;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 + i) + 16LL))(*((_QWORD *)v19 + i));
    }
    v10 = v19;
    v11 = (char *)v19 + 8 * i;
    v12 = RuntimeErrorWithScriptEnter - i;
    for ( j = 0; j < v12; ++j )
    {
      v14 = *(_QWORD *)&v11[8 * j];
      if ( v14 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 16LL))(*(_QWORD *)&v11[8 * j]);
        v10 = v19;
      }
    }
    CoTaskMemFree(v10);
    v19 = 0;
    CoTaskMemFree(v21[0]);
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x18024e84c  mov     r11, rsp
0x18024e84f  mov     [r11+8], rcx
0x18024e853  push    rdi
0x18024e854  push    r12
0x18024e856  push    r13
0x18024e858  push    r14
0x18024e85a  push    r15
0x18024e85c  sub     rsp, 80h
0x18024e863  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x18024e86b  mov     [r11+10h], rbx
0x18024e86f  mov     [r11+18h], rsi
0x18024e873  xor     r13d, r13d
0x18024e876  mov     [r11-68h], r13d
0x18024e87a  mov     [r11-60h], r13
0x18024e87e  mov     [r11-64h], r13d
0x18024e882  mov     [r11-58h], r13
0x18024e886  mov     [r11-50h], r13
0x18024e88a  mov     r14, rcx
0x18024e88d  mov     rax, [rcx+40h]
0x18024e891  mov     rcx, [rax+28h]
0x18024e895  mov     rax, [rcx]
0x18024e898  lea     rdx, [r11-50h]
0x18024e89c  mov     [r11-78h], rdx
0x18024e8a0  lea     rdx, [r11-58h]
0x18024e8a4  mov     [r11-80h], rdx
0x18024e8a8  lea     rdx, [r11-64h]
0x18024e8ac  mov     [rsp+0A8h+var_88], rdx
0x18024e8b1  lea     r9, [r11-60h]
0x18024e8b5  lea     r8, [r11-68h]
0x18024e8b9  mov     rdx, [r14+18h]
0x18024e8bd  mov     rax, [rax+30h]
0x18024e8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e8c6  mov     edi, eax
0x18024e8c8  test    eax, eax
0x18024e8ca  js      loc_18024EA5B
0x18024e8d0  mov     esi, r13d
0x18024e8d3  mov     ebx, [rsp+0A8h+var_2C]
0x18024e8d7  cmp     esi, [rsp+0A8h+var_64]
0x18024e8db  jnb     loc_18024E970
0x18024e8e1  mov     ecx, esi
0x18024e8e3  mov     rax, [rsp+0A8h+pv]
0x18024e8e8  mov     r15, [rax+rcx*8]
0x18024e8ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x18024e8f0  inc     rax
0x18024e8f3  cmp     [r15+rax*2], r13w
0x18024e8f8  jnz     short loc_18024E8F0
0x18024e8fa  lea     r12, [rax+1]
0x18024e8fe  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x18024e905  mov     [rsp+0A8h+var_38], rax
0x18024e90a  mov     [rsp+0A8h+var_30], r13d
0x18024e90f  mov     [rsp+0A8h+var_2C], ebx
0x18024e913  mov     rcx, [r14+40h]
0x18024e917  mov     r8, r12
0x18024e91a  lea     rdx, [rsp+0A8h+var_38]
0x18024e91f  mov     rcx, [rcx+18h]
0x18024e923  call    ??$AllocateArray@VArenaAllocator@@G$0A@@@YAPEAGPEAVArenaAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<ArenaAllocator,ushort,0>(ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64),unsigned __int64)
0x18024e928  mov     r13, rax
0x18024e92b  mov     r8, r15; Source
0x18024e92e  mov     rdx, r12; SizeInWords
0x18024e931  mov     rcx, rax; Destination
0x18024e934  call    cs:__imp_wcscpy_s
0x18024e93a  mov     r8, [r14+40h]
0x18024e93e  mov     r8, [r8+18h]
0x18024e942  mov     rdx, r13
0x18024e945  mov     rcx, [r14+20h]
0x18024e949  call    ?Prepend@?$ImmutableList@PEBUProperty@ProjectionModel@@@regex@@QEAAPEAV12@PEBUProperty@ProjectionModel@@PEAVArenaAllocator@@@Z; regex::ImmutableList<ProjectionModel::Property const *>::Prepend(ProjectionModel::Property const *,ArenaAllocator *)
0x18024e94e  mov     [r14+20h], rax
0x18024e952  mov     rcx, r15; pv
0x18024e955  call    cs:__imp_CoTaskMemFree
0x18024e95b  mov     rax, [rsp+0A8h+pv]
0x18024e960  mov     ecx, esi
0x18024e962  xor     r13d, r13d
0x18024e965  mov     [rax+rcx*8], r13
0x18024e969  inc     esi
0x18024e96b  jmp     loc_18024E8D7
0x18024e970  mov     rcx, [rsp+0A8h+pv]; pv
0x18024e975  call    cs:__imp_CoTaskMemFree
0x18024e97b  mov     [rsp+0A8h+pv], r13
0x18024e980  mov     ebx, r13d
0x18024e983  cmp     ebx, [rsp+0A8h+var_68]
0x18024e987  jnb     loc_18024EA1E
0x18024e98d  mov     esi, ebx
0x18024e98f  mov     r8, [rsp+0A8h+var_50]
0x18024e994  mov     r8d, [r8+rsi*4]; int
0x18024e998  mov     rdx, [rsp+0A8h+var_60]
0x18024e99d  mov     rdx, [rdx+rsi*8]; struct IUnknown *
0x18024e9a1  mov     rcx, r14; this
0x18024e9a4  call    ?AddDirectChildTypesFromMetadata@NamespaceProjection@Projection@@AEAAJPEAUIUnknown@@H@Z; Projection::NamespaceProjection::AddDirectChildTypesFromMetadata(IUnknown *,int)
0x18024e9a9  mov     edi, eax
0x18024e9ab  test    eax, eax
0x18024e9ad  jns     short loc_18024EA02
0x18024e9af  mov     rcx, [rsp+0A8h+var_60]; pv
0x18024e9b4  lea     r14, [rcx+rsi*8]
0x18024e9b8  mov     esi, [rsp+0A8h+var_68]
0x18024e9bc  sub     esi, ebx
0x18024e9be  mov     ebx, r13d
0x18024e9c1  cmp     ebx, esi
0x18024e9c3  jnb     short loc_18024E9E8
0x18024e9c5  mov     eax, ebx
0x18024e9c7  mov     rdx, [r14+rax*8]
0x18024e9cb  test    rdx, rdx
0x18024e9ce  jz      short loc_18024E9E4
0x18024e9d0  mov     rax, [rdx]
0x18024e9d3  mov     rcx, rdx
0x18024e9d6  mov     rax, [rax+10h]
0x18024e9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e9df  mov     rcx, [rsp+0A8h+var_60]
0x18024e9e4  inc     ebx
0x18024e9e6  jmp     short loc_18024E9C1
0x18024e9e8  call    cs:__imp_CoTaskMemFree
0x18024e9ee  mov     [rsp+0A8h+var_60], r13
0x18024e9f3  mov     rcx, [rsp+0A8h+var_50]; pv
0x18024e9f8  call    cs:__imp_CoTaskMemFree
0x18024e9fe  mov     eax, edi
0x18024ea00  jmp     short loc_18024EA5B
0x18024ea02  mov     rax, [rsp+0A8h+var_60]
0x18024ea07  mov     rcx, [rax+rsi*8]
0x18024ea0b  mov     rax, [rcx]
0x18024ea0e  mov     rax, [rax+10h]
0x18024ea12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024ea17  inc     ebx
0x18024ea19  jmp     loc_18024E983
0x18024ea1e  mov     rcx, [r14+20h]
0x18024ea22  call    ?SortCurrentList@?$ImmutableList@PEBG@regex@@QEAAPEAV12@PEAU?$Comparer@PEAPEBG@2@@Z; regex::ImmutableList<ushort const *>::SortCurrentList(regex::Comparer<ushort const * *> *)
0x18024ea27  mov     [r14+20h], rax
0x18024ea2b  mov     rcx, [rsp+0A8h+var_60]; pv
0x18024ea30  call    cs:__imp_CoTaskMemFree
0x18024ea36  mov     [rsp+0A8h+var_60], r13
0x18024ea3b  mov     rcx, [rsp+0A8h+var_50]; pv
0x18024ea40  call    cs:__imp_CoTaskMemFree
0x18024ea46  nop
0x18024ea47  jmp     short loc_18024EA59
0x18024ea49  jmp     short loc_18024EA55
0x18024ea4b  jmp     short loc_18024EA55
0x18024ea4d  jmp     short loc_18024EA55
0x18024ea4f  jmp     short loc_18024EA55
0x18024ea51  jmp     short loc_18024EA55
0x18024ea53  jmp     short $+2
0x18024ea55  mov     edi, [rsp+0A8h+var_68]
0x18024ea59  mov     eax, edi
0x18024ea5b  lea     r11, [rsp+0A8h+var_28]
0x18024ea63  mov     rbx, [r11+38h]
0x18024ea67  mov     rsi, [r11+40h]
0x18024ea6b  mov     rsp, r11
0x18024ea6e  pop     r15
0x18024ea70  pop     r14
0x18024ea72  pop     r13
0x18024ea74  pop     r12
0x18024ea76  pop     rdi
0x18024ea77  retn
```
