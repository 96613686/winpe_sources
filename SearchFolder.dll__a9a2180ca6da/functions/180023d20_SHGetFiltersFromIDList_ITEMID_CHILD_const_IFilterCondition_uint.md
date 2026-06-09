# SHGetFiltersFromIDList(_ITEMID_CHILD const *,IFilterCondition * * *,uint *)

- ea: `0x180023d20`
- end: `0x180023e60`
- name: `?SHGetFiltersFromIDList@@YAJPEFBU_ITEMID_CHILD@@PEAPEAPEAUIFilterCondition@@PEAI@Z`
- size: `320`
- prototype: `__int64 __fastcall(const struct _ITEMID_CHILD *, struct IFilterCondition ***, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180023a1c`
- `0x180023fb0`
- `0x18003ce0c`

## callees

- `0x180009d00`
- `0x18000bb60`
- `0x18000f718`
- `0x180022b8c`
- `0x180023d20`
- `0x180023e68`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180023db5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180023db5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180023d99`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180023d99`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180023d84`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180023d84`

## pseudocode

```c
__int64 __fastcall SHGetFiltersFromIDList(
        const struct _ITEMID_CHILD *a1,
        struct IFilterCondition ***a2,
        unsigned int *a3)
{
  HRESULT v5; // ebx
  const BYTE *v6; // rcx
  __int64 v7; // rdx
  IStream *v8; // rax
  IStream *v9; // rsi
  struct IFilterCondition **v10; // rdi
  const struct _GUID *v11; // rdx
  void *v12; // rcx
  int v13; // eax
  __int64 v14; // rbp
  unsigned int v15; // eax
  int v16; // eax
  unsigned int pv; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp+18h] BYREF
  void *v20; // [rsp+68h] [rbp+20h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = 1;
  v6 = (const BYTE *)ILFindHiddenIDOn(a1, 3203334160LL);
  if ( v6 )
  {
    if ( !*((_WORD *)v6 + 1) )
    {
      v7 = *(unsigned __int16 *)v6;
      if ( v7 != 8 )
      {
        v5 = -2147024882;
        v8 = SHCreateMemStream(v6 + 8, (int)v7 - 8);
        v9 = v8;
        if ( v8 )
        {
          IStream_Reset(v8);
          pv = 0;
          v5 = IStream_Read(v9, &pv, 4u);
          if ( v5 >= 0 )
          {
            v5 = 1;
            if ( pv )
            {
              v10 = 0;
              v20 = 0;
              v19 = 0;
              v5 = ULongLongMult(pv, 8u, &v19);
              if ( v5 >= 0 )
              {
                v13 = CTCoAllocPolicy::Alloc(v12, 1u, v19, &v20);
                v10 = (struct IFilterCondition **)v20;
                v5 = v13;
              }
              if ( v5 >= 0 )
              {
                v14 = 0;
                while ( 1 )
                {
                  v15 = pv;
                  if ( (unsigned int)v14 >= pv )
                    break;
                  v16 = SHLoadFilterFromStream(v9, v11, (void **)&v10[v14]);
                  v14 = (unsigned int)(v14 + 1);
                  v5 = v16;
                  if ( v16 < 0 )
                  {
                    FreeFilterArray(v10, pv);
                    goto LABEL_15;
                  }
                }
                *a2 = v10;
                *a3 = v15;
              }
            }
          }
LABEL_15:
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180023d20  mov     [rsp+arg_0], rbx
0x180023d25  push    rbp
0x180023d26  push    rsi
0x180023d27  push    rdi
0x180023d28  push    r14
0x180023d2a  push    r15
0x180023d2c  sub     rsp, 20h
0x180023d30  mov     r15, rdx
0x180023d33  mov     qword ptr [rdx], 0
0x180023d3a  mov     edx, 0BEEF0010h
0x180023d3f  mov     dword ptr [r8], 0
0x180023d46  mov     r14, r8
0x180023d49  mov     ebx, 1
0x180023d4e  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x180023d53  mov     rcx, rax
0x180023d56  test    rax, rax
0x180023d59  jz      loc_180023E4D
0x180023d5f  xor     eax, eax
0x180023d61  cmp     ax, [rcx+2]
0x180023d65  jnz     loc_180023E4D
0x180023d6b  movzx   edx, word ptr [rcx]
0x180023d6e  cmp     rdx, 8
0x180023d72  jz      loc_180023E4D
0x180023d78  sub     edx, 8; cbInit
0x180023d7b  add     rcx, 8; pInit
0x180023d7f  mov     ebx, 8007000Eh
0x180023d84  call    cs:__imp_SHCreateMemStream
0x180023d8a  mov     rsi, rax
0x180023d8d  test    rax, rax
0x180023d90  jz      loc_180023E4D
0x180023d96  mov     rcx, rax; pstm
0x180023d99  call    cs:__imp_IStream_Reset
0x180023d9f  mov     r8d, 4; cb
0x180023da5  mov     [rsp+48h+pv], 0
0x180023dad  lea     rdx, [rsp+48h+pv]; pv
0x180023db2  mov     rcx, rsi; pstm
0x180023db5  call    cs:__imp_IStream_Read
0x180023dbb  mov     ebx, eax
0x180023dbd  test    eax, eax
0x180023dbf  js      short loc_180023E3E
0x180023dc1  mov     eax, [rsp+48h+pv]
0x180023dc5  mov     ebx, 1
0x180023dca  test    eax, eax
0x180023dcc  jz      short loc_180023E3E
0x180023dce  xor     edi, edi
0x180023dd0  lea     r8, [rsp+48h+arg_10]; unsigned __int64 *
0x180023dd5  mov     ecx, eax; unsigned __int64
0x180023dd7  mov     [rsp+48h+arg_18], rdi
0x180023ddc  lea     edx, [rbx+7]; unsigned __int64
0x180023ddf  mov     [rsp+48h+arg_10], rdi
0x180023de4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180023de9  mov     ebx, eax
0x180023deb  test    eax, eax
0x180023ded  js      short loc_180023E08
0x180023def  mov     r8, [rsp+48h+arg_10]; unsigned __int64
0x180023df4  lea     r9, [rsp+48h+arg_18]; void **
0x180023df9  lea     edx, [rdi+1]; unsigned int
0x180023dfc  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180023e01  mov     rdi, [rsp+48h+arg_18]
0x180023e06  mov     ebx, eax
0x180023e08  test    ebx, ebx
0x180023e0a  js      short loc_180023E3E
0x180023e0c  xor     ebp, ebp
0x180023e0e  mov     eax, [rsp+48h+pv]
0x180023e12  cmp     ebp, eax
0x180023e14  jnb     short loc_180023E38
0x180023e16  lea     r8, [rdi+rbp*8]; void **
0x180023e1a  mov     rcx, rsi; struct IStream *
0x180023e1d  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x180023e22  inc     ebp
0x180023e24  mov     ebx, eax
0x180023e26  test    eax, eax
0x180023e28  jns     short loc_180023E0E
0x180023e2a  mov     edx, [rsp+48h+pv]; unsigned int
0x180023e2e  mov     rcx, rdi; pv
0x180023e31  call    ?FreeFilterArray@@YAXPEAPEAUIFilterCondition@@I@Z; FreeFilterArray(IFilterCondition * *,uint)
0x180023e36  jmp     short loc_180023E3E
0x180023e38  mov     [r15], rdi
0x180023e3b  mov     [r14], eax
0x180023e3e  mov     rax, [rsi]
0x180023e41  mov     rcx, rsi
0x180023e44  mov     rax, [rax+10h]
0x180023e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e4d  mov     eax, ebx
0x180023e4f  mov     rbx, [rsp+48h+arg_0]
0x180023e54  add     rsp, 20h
0x180023e58  pop     r15
0x180023e5a  pop     r14
0x180023e5c  pop     rdi
0x180023e5d  pop     rsi
0x180023e5e  pop     rbp
0x180023e5f  retn
```
