# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,uint)

- ea: `0x40b431`
- end: `0x40b4ea`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SG_NPAUFailureInfo@3@PAV123@PADI@Z`
- size: `185`
- prototype: `bool __userpurge@<al>(int@<edx>, int@<ecx>, struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x40b431`
- `0x40b4f0`

## callees

- `0x40b431`

## import_xrefs

- `msvcrt!memcpy_s` at `0x40b4d3`
- `msvcrt!memcpy_s` at `0x40b4d3`

## pseudocode

```c
bool __userpurge wil::details::ThreadFailureCallbackHolder::GetThreadContext@<al>(
        int a1@<edx>,
        int a2@<ecx>,
        struct wil::FailureInfo *a3,
        struct wil::details::ThreadFailureCallbackHolder *a4,
        char *a5,
        unsigned int a6)
{
  bool result; // al
  int v8; // edi
  int v9; // edx
  _DWORD *v10; // edi
  _DWORD *v11; // edi
  struct wil::details::ThreadFailureCallbackHolder *v12; // ecx
  struct wil::details::ThreadFailureCallbackHolder *v13; // ebx
  unsigned int v14; // ecx
  char *v15; // edi
  rsize_t v16; // esi
  char *v17; // [esp+0h] [ebp-10h]
  unsigned int v18; // [esp+4h] [ebp-Ch]

  result = 0;
  v8 = a2;
  *(_BYTE *)a3 = 0;
  if ( a1 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a3, a4, v17, v18);
    v9 = *(_DWORD *)(a1 + 16);
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*(_DWORD *)(v8 + 52) )
      {
        v10 = (_DWORD *)(v8 + 52);
        *v10++ = *(_DWORD *)v9;
        *v10 = *(_DWORD *)(v9 + 4);
        v10[1] = *(_DWORD *)(v9 + 8);
        v8 = a2;
      }
      v11 = (_DWORD *)(v8 + 64);
      *v11++ = *(_DWORD *)v9;
      *v11 = *(_DWORD *)(v9 + 4);
      v11[1] = *(_DWORD *)(v9 + 8);
      v12 = (struct wil::FailureInfo *)((char *)a3 + strlen((const char *)a3) + 1);
      if ( (int)a4 + (int)a3 - ((int)v12 - 1) > 2 )
      {
        *((_BYTE *)v12 - 1) = 92;
        v13 = v12;
        v14 = strlen(*(const char **)(v9 + 4));
        v15 = (char *)((struct wil::details::ThreadFailureCallbackHolder *)((char *)a4 + (_DWORD)a3) - v13);
        v16 = (rsize_t)v15;
        if ( v14 + 1 < (unsigned int)v15 )
          v16 = v14 + 1;
        _memcpy_s(v13, (const rsize_t)v15, *(const void *const *)(v9 + 4), v16);
        *((_BYTE *)v13 + v16 - 1) = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40b431  mov     edi, edi
0x40b433  push    ebp
0x40b434  mov     ebp, esp
0x40b436  push    ecx
0x40b437  push    ebx
0x40b438  mov     ebx, [ebp+arg_0]
0x40b43b  xor     al, al
0x40b43d  push    esi; unsigned int
0x40b43e  push    edi; char *
0x40b43f  mov     esi, edx
0x40b441  mov     edi, ecx
0x40b443  mov     [ebp+var_4], edi
0x40b446  mov     byte ptr [ebx], 0
0x40b449  test    esi, esi
0x40b44b  jz      loc_40B4E3
0x40b451  push    [ebp+arg_4]; struct wil::details::ThreadFailureCallbackHolder *
0x40b454  mov     edx, [esi+8]
0x40b457  push    ebx; struct wil::FailureInfo *
0x40b458  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SG_NPAUFailureInfo@3@PAV123@PADI@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,uint)
0x40b45d  mov     edx, [esi+10h]
0x40b460  test    edx, edx
0x40b462  jz      short loc_40B4E3
0x40b464  cmp     dword ptr [edx], 0
0x40b467  jnz     short loc_40B477
0x40b469  xor     eax, eax
0x40b46b  inc     eax
0x40b46c  lock xadd ?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x40b474  inc     eax
0x40b475  mov     [edx], eax
0x40b477  cmp     dword ptr [edi+34h], 0
0x40b47b  jnz     short loc_40B488
0x40b47d  mov     esi, edx
0x40b47f  lea     edi, [edi+34h]
0x40b482  movsd
0x40b483  movsd
0x40b484  movsd
0x40b485  mov     edi, [ebp+var_4]
0x40b488  add     edi, 40h ; '@'
0x40b48b  mov     esi, edx
0x40b48d  mov     ecx, ebx
0x40b48f  movsd
0x40b490  movsd
0x40b491  movsd
0x40b492  mov     edi, [ebp+arg_4]
0x40b495  lea     esi, [ecx+1]
0x40b498  add     edi, ebx
0x40b49a  mov     al, [ecx]
0x40b49c  inc     ecx
0x40b49d  test    al, al
0x40b49f  jnz     short loc_40B49A
0x40b4a1  sub     ecx, esi
0x40b4a3  mov     eax, edi
0x40b4a5  add     ebx, ecx
0x40b4a7  sub     eax, ebx
0x40b4a9  cmp     eax, 2
0x40b4ac  jle     short loc_40B4E1
0x40b4ae  mov     byte ptr [ebx], 5Ch ; '\'
0x40b4b1  inc     ebx
0x40b4b2  mov     ecx, [edx+4]
0x40b4b5  lea     esi, [ecx+1]
0x40b4b8  mov     al, [ecx]
0x40b4ba  inc     ecx
0x40b4bb  test    al, al
0x40b4bd  jnz     short loc_40B4B8
0x40b4bf  sub     ecx, esi
0x40b4c1  sub     edi, ebx
0x40b4c3  mov     esi, edi
0x40b4c5  lea     eax, [ecx+1]
0x40b4c8  cmp     eax, edi
0x40b4ca  cmovb   esi, eax
0x40b4cd  push    esi; SourceSize
0x40b4ce  push    dword ptr [edx+4]; Source
0x40b4d1  push    edi; DestinationSize
0x40b4d2  push    ebx; Destination
0x40b4d3  call    ds:__imp__memcpy_s
0x40b4d9  add     esp, 10h
0x40b4dc  mov     byte ptr [esi+ebx-1], 0
0x40b4e1  mov     al, 1
0x40b4e3  pop     edi
0x40b4e4  pop     esi
0x40b4e5  pop     ebx
0x40b4e6  leave
0x40b4e7  retn    8
```
