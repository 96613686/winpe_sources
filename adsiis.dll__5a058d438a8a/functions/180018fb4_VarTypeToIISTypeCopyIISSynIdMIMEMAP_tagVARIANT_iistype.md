# VarTypeToIISTypeCopyIISSynIdMIMEMAP(tagVARIANT *,_iistype *)

- ea: `0x180018fb4`
- end: `0x180019085`
- name: `?VarTypeToIISTypeCopyIISSynIdMIMEMAP@@YAJPEAUtagVARIANT@@PEAU_iistype@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct tagVARIANT *, struct _iistype *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018a44`

## callees

- `0x18000dd4c`
- `0x180018fb4`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180018ff7`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180018ff7`

## pseudocode

```c
__int64 __fastcall VarTypeToIISTypeCopyIISSynIdMIMEMAP(struct tagVARIANT *a1, struct _iistype *a2)
{
  bool v3; // zf
  _WORD *v4; // rcx
  __int64 result; // rax
  int v6; // ebx
  CMimeType *v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp+10h] BYREF

  *((_QWORD *)a2 + 1) = 0;
  *(_DWORD *)a2 = 8;
  v3 = a1->vt == 9;
  v8 = 0;
  v7 = 0;
  if ( v3 )
  {
    if ( (**(int (__fastcall ***)(LONGLONG, GUID *, CMimeType **))a1->llVal)(a1->llVal, &IID_IISMimeType, &v7) >= 0 )
    {
      v6 = CMimeType::CopyMimeType(v7, &v8);
      if ( v6 >= 0 )
        *((_QWORD *)a2 + 1) = v8;
    }
    else
    {
      v6 = -2147463156;
    }
    if ( v7 )
      (*(void (__fastcall **)(CMimeType *))(*(_QWORD *)v7 + 16LL))(v7);
    return (unsigned int)v6;
  }
  else if ( a1->vt != 8 || a1->llVal )
  {
    return 2147504140LL;
  }
  else
  {
    v4 = AllocADsMem(2u);
    if ( v4 )
    {
      result = 0;
      *v4 = 0;
      *((_QWORD *)a2 + 1) = v4;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018fb4  mov     [rsp+arg_10], rbx
0x180018fb9  push    rdi
0x180018fba  sub     rsp, 20h
0x180018fbe  mov     eax, 8
0x180018fc3  mov     qword ptr [rdx+8], 0
0x180018fcb  mov     [rdx], eax
0x180018fcd  mov     rdi, rdx
0x180018fd0  cmp     word ptr [rcx], 9
0x180018fd4  mov     [rsp+28h+arg_8], 0
0x180018fdd  mov     [rsp+28h+arg_0], 0
0x180018fe6  jz      short loc_18001901E
0x180018fe8  cmp     [rcx], ax
0x180018feb  jnz     short loc_180019017
0x180018fed  cmp     qword ptr [rcx+8], 0
0x180018ff2  jnz     short loc_180019017
0x180018ff4  lea     ecx, [rax-6]; cb
0x180018ff7  call    cs:__imp_AllocADsMem
0x180018ffd  mov     rcx, rax
0x180019000  test    rax, rax
0x180019003  jnz     short loc_18001900C
0x180019005  mov     eax, 8007000Eh
0x18001900a  jmp     short loc_18001907A
0x18001900c  xor     eax, eax
0x18001900e  mov     [rcx], ax
0x180019011  mov     [rdi+8], rcx
0x180019015  jmp     short loc_18001907A
0x180019017  mov     eax, 8000500Ch
0x18001901c  jmp     short loc_18001907A
0x18001901e  mov     rcx, [rcx+8]
0x180019022  lea     r8, [rsp+28h+arg_0]
0x180019027  lea     rdx, IID_IISMimeType
0x18001902e  mov     rax, [rcx]
0x180019031  mov     rax, [rax]
0x180019034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019039  test    eax, eax
0x18001903b  jns     short loc_180019044
0x18001903d  mov     ebx, 8000500Ch
0x180019042  jmp     short loc_180019062
0x180019044  mov     rcx, [rsp+28h+arg_0]; this
0x180019049  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 **
0x18001904e  call    ?CopyMimeType@CMimeType@@QEAAJPEAPEAG@Z; CMimeType::CopyMimeType(ushort * *)
0x180019053  mov     ebx, eax
0x180019055  test    eax, eax
0x180019057  js      short loc_180019062
0x180019059  mov     rcx, [rsp+28h+arg_8]
0x18001905e  mov     [rdi+8], rcx
0x180019062  mov     rcx, [rsp+28h+arg_0]
0x180019067  test    rcx, rcx
0x18001906a  jz      short loc_180019078
0x18001906c  mov     rdx, [rcx]
0x18001906f  mov     rax, [rdx+10h]
0x180019073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019078  mov     eax, ebx
0x18001907a  mov     rbx, [rsp+28h+arg_10]
0x18001907f  add     rsp, 20h
0x180019083  pop     rdi
0x180019084  retn
```
