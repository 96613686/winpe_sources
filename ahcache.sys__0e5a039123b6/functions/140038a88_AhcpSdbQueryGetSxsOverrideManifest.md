# AhcpSdbQueryGetSxsOverrideManifest

- ea: `0x140038a88`
- end: `0x140038bd2`
- name: `AhcpSdbQueryGetSxsOverrideManifest`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140059d78`

## callees

- `0x140007b40`
- `0x140038a88`
- `0x14003a2a8`
- `0x14003a364`
- `0x14003e364`
- `0x14003ef10`
- `0x14005498c`

## string_xrefs

- `0x140038b62`: `AhcpSdbQueryGetSxsOverrideManifest`
- `0x140038b32`: `Failed to get sxs manifest string [%x]`
- `0x140038b51`: `Failed to allocate sxs manifest buffer [%x]`

## pseudocode

```c
__int64 __fastcall AhcpSdbQueryGetSxsOverrideManifest(_QWORD *a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int FirstTagRef; // eax
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v14; // rcx
  _WORD *StringTagPtr; // rbx
  __int64 v16; // rax
  int v17; // esi
  unsigned int v18; // ebp
  void *v19; // rax
  void *v20; // rdi
  int v21; // [rsp+20h] [rbp-48h]
  PVOID v22[7]; // [rsp+30h] [rbp-38h] BYREF
  int v23; // [rsp+88h] [rbp+20h] BYREF

  v22[0] = 0;
  v8 = 0;
  v23 = 0;
  if ( *(_DWORD *)(a4 + 168) )
  {
    while ( 1 )
    {
      FirstTagRef = SdbFindFirstTagRef(a3, *(unsigned int *)(a4 + 4LL * v8), 24605);
      if ( FirstTagRef )
        break;
      if ( ++v8 >= *(_DWORD *)(a4 + 168) )
        goto LABEL_2;
    }
    if ( (unsigned int)SdbTagRefToTagID(a3, FirstTagRef, v22, &v23) )
    {
      StringTagPtr = (_WORD *)SdbGetStringTagPtr(v22[0]);
      if ( StringTagPtr )
      {
        v16 = -1;
        do
          ++v16;
        while ( StringTagPtr[v16] );
        v17 = 2 * v16;
        v18 = 2 * v16;
        v19 = (void *)AslAlloc(v14, (unsigned int)(2 * v16), 1);
        v20 = v19;
        if ( v19 )
        {
          memmove(v19, StringTagPtr, v18);
          *a1 = v20;
          *a2 = v17;
          return 0;
        }
        v9 = -1073741801;
        v12 = "Failed to allocate sxs manifest buffer [%x]";
        v21 = -1073741801;
        v13 = 1089;
LABEL_13:
        AslLogCallPrintf(1, "AhcpSdbQueryGetSxsOverrideManifest", v13, v12, v21);
        return v9;
      }
      v12 = "Failed to get sxs manifest string [%x]";
      v13 = 1076;
    }
    else
    {
      v12 = "Failed to convert tagref to tagid [%x]";
      v13 = 1065;
    }
    v21 = -1073741480;
    v9 = -1073741480;
    goto LABEL_13;
  }
LABEL_2:
  *a1 = 0;
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x140038a88  mov     rax, rsp
0x140038a8b  mov     [rax+8], rbx
0x140038a8f  mov     [rax+10h], rbp
0x140038a93  push    rsi
0x140038a94  push    rdi
0x140038a95  push    r12
0x140038a97  push    r14
0x140038a99  push    r15
0x140038a9b  sub     rsp, 40h
0x140038a9f  xor     r12d, r12d
0x140038aa2  mov     rdi, r9
0x140038aa5  mov     rsi, r8
0x140038aa8  mov     r14, rdx
0x140038aab  mov     r15, rcx
0x140038aae  mov     [rax-38h], r12
0x140038ab2  mov     ebx, r12d
0x140038ab5  mov     [rax+20h], r12d
0x140038ab9  cmp     [r9+0A8h], r12d
0x140038ac0  ja      short loc_140038AE5
0x140038ac2  mov     [r15], r12
0x140038ac5  mov     [r14], r12d
0x140038ac8  mov     ebx, r12d
0x140038acb  mov     rbp, [rsp+68h+arg_8]
0x140038ad0  mov     eax, ebx
0x140038ad2  mov     rbx, [rsp+68h+arg_0]
0x140038ad7  add     rsp, 40h
0x140038adb  pop     r15
0x140038add  pop     r14
0x140038adf  pop     r12
0x140038ae1  pop     rdi
0x140038ae2  pop     rsi
0x140038ae3  retn
0x140038ae5  mov     edx, ebx
0x140038ae7  mov     r8d, 601Dh
0x140038aed  mov     rcx, rsi
0x140038af0  mov     edx, [rdi+rdx*4]
0x140038af3  call    SdbFindFirstTagRef
0x140038af8  test    eax, eax
0x140038afa  jnz     short loc_140038B08
0x140038afc  inc     ebx
0x140038afe  cmp     ebx, [rdi+0A8h]
0x140038b04  jb      short loc_140038AE5
0x140038b06  jmp     short loc_140038AC2
0x140038b08  lea     r9, [rsp+68h+arg_18]
0x140038b10  mov     edx, eax
0x140038b12  lea     r8, [rsp+68h+var_38]
0x140038b17  mov     rcx, rsi
0x140038b1a  call    SdbTagRefToTagID
0x140038b1f  test    eax, eax
0x140038b21  jnz     short loc_140038B78
0x140038b23  lea     r9, aFailedToConver_5; "Failed to convert tagref to tagid [%x]"
0x140038b2a  mov     r8d, 429h
0x140038b30  jmp     short loc_140038B3F
0x140038b32  lea     r9, aFailedToGetSxs; "Failed to get sxs manifest string [%x]"
0x140038b39  mov     r8d, 434h
0x140038b3f  mov     eax, 0C0000158h
0x140038b44  mov     [rsp+68h+var_48], eax
0x140038b48  mov     ebx, eax
0x140038b4a  jmp     short loc_140038B62
0x140038b4c  mov     ebx, 0C0000017h
0x140038b51  lea     r9, aFailedToAlloca_25; "Failed to allocate sxs manifest buffer "...
0x140038b58  mov     [rsp+68h+var_48], ebx
0x140038b5c  mov     r8d, 441h
0x140038b62  lea     rdx, aAhcpsdbqueryge; "AhcpSdbQueryGetSxsOverrideManifest"
0x140038b69  mov     ecx, 1
0x140038b6e  call    AslLogCallPrintf
0x140038b73  jmp     loc_140038ACB
0x140038b78  mov     edx, [rsp+68h+arg_18]
0x140038b7f  mov     rcx, [rsp+68h+var_38]
0x140038b84  call    SdbGetStringTagPtr
0x140038b89  mov     rbx, rax
0x140038b8c  test    rax, rax
0x140038b8f  jz      short loc_140038B32
0x140038b91  or      rax, 0FFFFFFFFFFFFFFFFh
0x140038b95  inc     rax
0x140038b98  cmp     [rbx+rax*2], r12w
0x140038b9d  jnz     short loc_140038B95
0x140038b9f  lea     esi, [rax+rax]
0x140038ba2  mov     r8d, 1
0x140038ba8  mov     edx, esi
0x140038baa  mov     ebp, esi
0x140038bac  call    AslAlloc
0x140038bb1  mov     rdi, rax
0x140038bb4  test    rax, rax
0x140038bb7  jz      short loc_140038B4C
0x140038bb9  mov     r8d, ebp; Size
0x140038bbc  mov     rdx, rbx; Src
0x140038bbf  mov     rcx, rax; void *
0x140038bc2  call    memmove
0x140038bc7  mov     [r15], rdi
0x140038bca  mov     [r14], esi
0x140038bcd  jmp     loc_140038AC8
```
