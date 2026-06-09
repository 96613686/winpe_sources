# DestroyContext

- ea: `0x18007af58`
- end: `0x18007b040`
- name: `DestroyContext`
- size: `232`
- prototype: `HRESULT __stdcall(HRECOCONTEXT hrc)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006978c`
- `0x180069860`
- `0x1800a31dc`
- `0x1800a4810`
- `0x1800c532c`
- `0x1800fb890`

## callees

- `0x180079bdc`
- `0x18007af58`
- `0x180083dc0`
- `0x180086154`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007afad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007afad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007afe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007afe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b02d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b02d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18007afd9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18007afd9`

## pseudocode

```c
HRESULT __stdcall DestroyContext(HRECOCONTEXT hrc)
{
  int v3; // ebx
  HRESULT v4; // edi
  HRESULT v5; // ebx
  void *v6; // rcx
  DWORD dwindex; // [rsp+40h] [rbp+8h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp+10h] BYREF

  pHandles = 0;
  if ( !hrc )
    return 0;
  if ( *((_QWORD *)hrc + 2) )
  {
    AdviseInkChange(hrc, 1);
    v3 = *((_DWORD *)hrc + 6);
    pHandles = (HANDLE)*((_QWORD *)hrc + 2);
    *((_DWORD *)hrc + 23) = 0;
    v4 = AddToQueue(hrc, 0, 0);
    if ( v3 != GetCurrentThreadId() )
    {
      dwindex = 0;
      CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
    }
    CloseHandle(pHandles);
    return v4;
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)hrc + 40LL))(*((_QWORD *)hrc + 1));
    WispTraceInformationIf(v5 < 0, "%s - RecoAPIs::DestroyContext failed.\n", "DestroyContext");
    v6 = (void *)*((_QWORD *)hrc + 5);
    if ( v6 )
      CoTaskMemFree(v6);
    CoTaskMemFree(hrc);
    return v5;
  }
}

```

## disassembly

```asm
0x18007af58  mov     [rsp+arg_10], rbx
0x18007af5d  push    rdi
0x18007af5e  sub     rsp, 30h
0x18007af62  mov     [rsp+38h+pHandles], 0
0x18007af6b  mov     rdi, rcx
0x18007af6e  test    rcx, rcx
0x18007af71  jnz     short loc_18007AF7A
0x18007af73  xor     eax, eax
0x18007af75  jmp     loc_18007B035
0x18007af7a  cmp     qword ptr [rcx+10h], 0
0x18007af7f  jz      short loc_18007AFEE
0x18007af81  mov     edx, 1; bNewStroke
0x18007af86  call    AdviseInkChange
0x18007af8b  mov     rax, [rdi+10h]
0x18007af8f  xor     r8d, r8d
0x18007af92  mov     ebx, [rdi+18h]
0x18007af95  xor     edx, edx
0x18007af97  mov     rcx, rdi
0x18007af9a  mov     [rsp+38h+pHandles], rax
0x18007af9f  mov     dword ptr [rdi+5Ch], 0
0x18007afa6  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x18007afab  mov     edi, eax
0x18007afad  call    cs:__imp_GetCurrentThreadId
0x18007afb3  cmp     ebx, eax
0x18007afb5  jz      short loc_18007AFDF
0x18007afb7  lea     rax, [rsp+38h+dwindex]
0x18007afbc  mov     [rsp+38h+dwindex], 0
0x18007afc4  lea     r9, [rsp+38h+pHandles]; pHandles
0x18007afc9  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18007afce  mov     r8d, 1; cHandles
0x18007afd4  or      edx, 0FFFFFFFFh; dwTimeout
0x18007afd7  xor     ecx, ecx; dwFlags
0x18007afd9  call    cs:__imp_CoWaitForMultipleHandles
0x18007afdf  mov     rcx, [rsp+38h+pHandles]; hObject
0x18007afe4  call    cs:__imp_CloseHandle
0x18007afea  mov     eax, edi
0x18007afec  jmp     short loc_18007B035
0x18007afee  mov     rax, [rcx]
0x18007aff1  mov     rcx, [rcx+8]
0x18007aff5  mov     rax, [rax+28h]
0x18007aff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007affe  mov     ecx, eax
0x18007b000  lea     r8, aDestroycontext; "DestroyContext"
0x18007b007  shr     ecx, 1Fh
0x18007b00a  lea     rdx, aSRecoapisDestr_0; "%s - RecoAPIs::DestroyContext failed.\n"
0x18007b011  movzx   ecx, cl; bool
0x18007b014  mov     ebx, eax
0x18007b016  call    ?WispTraceInformationIf@@YAX_NPEBDZZ; WispTraceInformationIf(bool,char const *,...)
0x18007b01b  mov     rcx, [rdi+28h]; pv
0x18007b01f  test    rcx, rcx
0x18007b022  jz      short loc_18007B02A
0x18007b024  call    cs:__imp_CoTaskMemFree
0x18007b02a  mov     rcx, rdi; pv
0x18007b02d  call    cs:__imp_CoTaskMemFree
0x18007b033  mov     eax, ebx
0x18007b035  mov     rbx, [rsp+38h+arg_10]
0x18007b03a  add     rsp, 30h
0x18007b03e  pop     rdi
0x18007b03f  retn
```
