# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)

- ea: `0x40b4f0`
- end: `0x40b5d5`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SGXPAUFailureInfo@3@PADI@Z`
- size: `229`
- prototype: `void __userpurge(struct wil::FailureInfo *@<edx>, int@<ecx>, struct wil::FailureInfo *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x40b5e0`

## callees

- `0x40b431`
- `0x40b4f0`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40b518`
- `KERNEL32!GetCurrentThreadId` at `0x40b518`

## pseudocode

```c
void __userpurge wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1@<edx>,
        int a2@<ecx>,
        struct wil::FailureInfo *a3,
        char *a4,
        unsigned int a5)
{
  char v7; // cl
  int v8; // ebx
  DWORD CurrentThreadId; // ecx
  int *i; // ebx
  int v11; // ebx
  char v12; // al
  bool v13; // al
  char *v14; // [esp+0h] [ebp-18h]
  unsigned int v15; // [esp+4h] [ebp-14h]
  char v16; // [esp+17h] [ebp-1h]

  v7 = 0;
  v16 = 0;
  *(_BYTE *)a1 = 0;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    for ( i = *(int **)(v8 + 4 * ((CurrentThreadId >> 2) % 0xA)); i; i = (int *)i[1] )
    {
      if ( *i == CurrentThreadId )
      {
        i += 2;
        break;
      }
    }
    if ( i && *i )
    {
      *(_BYTE *)a1 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a3, v14, v15) )
        *(_DWORD *)(a2 + 48) = a1;
      v11 = *i;
      do
      {
        v12 = *(_BYTE *)(v11 + 20);
        *(_BYTE *)(v11 + 20) = 1;
        if ( v12 )
        {
          v7 = v16;
        }
        else
        {
          v7 = (***(int (__thiscall ****)(_DWORD, int))(v11 + 4))(*(_DWORD *)(v11 + 4), a2) | v16;
          *(_BYTE *)(v11 + 20) = 0;
          v16 = v7;
        }
        v11 = *(_DWORD *)(v11 + 8);
      }
      while ( v11 );
    }
    else
    {
      v7 = 0;
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    v13 = v7 || (*(_BYTE *)(a2 + 4) & 2) != 0;
    wil::details::g_pfnTelemetryCallback(wil::details::g_pfnTelemetryCallback, v13, a2);
  }
}

```

## disassembly

```asm
0x40b4f0  mov     edi, edi
0x40b4f2  push    ebp
0x40b4f3  mov     ebp, esp
0x40b4f5  sub     esp, 0Ch
0x40b4f8  push    ebx
0x40b4f9  push    esi
0x40b4fa  push    edi
0x40b4fb  mov     edi, edx
0x40b4fd  mov     esi, ecx
0x40b4ff  xor     cl, cl
0x40b501  mov     [ebp+var_8], esi
0x40b504  mov     [ebp+var_1], cl
0x40b507  mov     byte ptr [edi], 0
0x40b50a  mov     ebx, ?g_pThreadFailureCallbacks@details@wil@@3PAV?$ThreadLocalStorage@PAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x40b510  test    ebx, ebx
0x40b512  jz      loc_40B5A7
0x40b518  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40b51e  mov     ecx, eax
0x40b520  mov     [ebp+var_C], 0Ah
0x40b527  shr     eax, 2
0x40b52a  xor     edx, edx
0x40b52c  div     [ebp+var_C]
0x40b52f  mov     ebx, [ebx+edx*4]
0x40b532  jmp     short loc_40B53B
0x40b534  cmp     [ebx], ecx
0x40b536  jz      short loc_40B590
0x40b538  mov     ebx, [ebx+4]
0x40b53b  test    ebx, ebx
0x40b53d  jnz     short loc_40B534
0x40b53f  test    ebx, ebx
0x40b541  jz      short loc_40B5A4
0x40b543  cmp     dword ptr [ebx], 0
0x40b546  jz      short loc_40B5A4
0x40b548  push    [ebp+arg_0]; struct wil::details::ThreadFailureCallbackHolder *
0x40b54b  mov     byte ptr [edi], 0
0x40b54e  mov     ecx, esi
0x40b550  mov     edx, [ebx]
0x40b552  push    edi; struct wil::FailureInfo *
0x40b553  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SG_NPAUFailureInfo@3@PAV123@PADI@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,uint)
0x40b558  test    al, al
0x40b55a  jz      short loc_40B55F
0x40b55c  mov     [esi+30h], edi
0x40b55f  mov     ebx, [ebx]
0x40b561  mov     al, [ebx+14h]
0x40b564  mov     byte ptr [ebx+14h], 1
0x40b568  test    al, al
0x40b56a  jnz     short loc_40B595
0x40b56c  mov     edi, [ebx+4]
0x40b56f  push    [ebp+var_8]
0x40b572  mov     eax, [edi]
0x40b574  mov     esi, [eax]
0x40b576  mov     ecx, esi
0x40b578  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40b57e  mov     ecx, edi
0x40b580  call    esi
0x40b582  mov     cl, [ebp+var_1]
0x40b585  or      cl, al
0x40b587  mov     byte ptr [ebx+14h], 0
0x40b58b  mov     [ebp+var_1], cl
0x40b58e  jmp     short loc_40B598
0x40b590  add     ebx, 8
0x40b593  jmp     short loc_40B53F
0x40b595  mov     cl, [ebp+var_1]
0x40b598  mov     ebx, [ebx+8]
0x40b59b  test    ebx, ebx
0x40b59d  jnz     short loc_40B561
0x40b59f  mov     esi, [ebp+var_8]
0x40b5a2  jmp     short loc_40B5A7
0x40b5a4  mov     cl, [ebp+var_1]
0x40b5a7  mov     edi, ?g_pfnTelemetryCallback@details@wil@@3P6GX_NABUFailureInfo@2@@_EA
0x40b5ad  test    edi, edi
0x40b5af  jz      short loc_40B5CE
0x40b5b1  test    cl, cl
0x40b5b3  jnz     short loc_40B5BF
0x40b5b5  test    byte ptr [esi+4], 2
0x40b5b9  jnz     short loc_40B5BF
0x40b5bb  xor     al, al
0x40b5bd  jmp     short loc_40B5C2
0x40b5bf  xor     eax, eax
0x40b5c1  inc     eax
0x40b5c2  push    esi
0x40b5c3  push    eax
0x40b5c4  mov     ecx, edi
0x40b5c6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40b5cc  call    edi ; ?g_pfnTelemetryCallback@details@wil@@3P6GX_NABUFailureInfo@2@@_EA
0x40b5ce  pop     edi
0x40b5cf  pop     esi
0x40b5d0  pop     ebx
0x40b5d1  leave
0x40b5d2  retn    4
```
