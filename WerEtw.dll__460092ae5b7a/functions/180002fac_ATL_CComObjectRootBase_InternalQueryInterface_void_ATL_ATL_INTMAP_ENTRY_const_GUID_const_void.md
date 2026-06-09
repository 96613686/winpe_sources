# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180002fac`
- end: `0x1800030b0`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800035e0`
- `0x1800078c0`
- `0x1800078e0`
- `0x180007900`
- `0x180007920`
- `0x18000bda0`
- `0x1800150a0`
- `0x180018210`
- `0x180019430`
- `0x18001e4f0`
- `0x1800219d0`
- `0x1800227a0`
- `0x180022b10`
- `0x1800246b0`

## callees

- `0x180002fac`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x180002fac  push    rbx
0x180002fae  push    rbp
0x180002faf  push    rsi
0x180002fb0  push    rdi
0x180002fb1  push    r14
0x180002fb3  sub     rsp, 30h
0x180002fb7  mov     rsi, r9
0x180002fba  mov     rdi, r8
0x180002fbd  mov     rbx, rdx
0x180002fc0  mov     r14, rcx
0x180002fc3  test    rcx, rcx
0x180002fc6  jz      loc_1800030A0
0x180002fcc  test    rdx, rdx
0x180002fcf  jz      loc_1800030A0
0x180002fd5  test    r9, r9
0x180002fd8  jnz     short loc_180002FE4
0x180002fda  mov     eax, 80004003h
0x180002fdf  jmp     loc_1800030A5
0x180002fe4  mov     qword ptr [r9], 0
0x180002feb  cmp     dword ptr [r8], 0
0x180002fef  jnz     short loc_180003029
0x180002ff1  cmp     dword ptr [r8+4], 0
0x180002ff6  jnz     short loc_180003029
0x180002ff8  cmp     dword ptr [r8+8], 0C0h
0x180003000  jnz     short loc_180003029
0x180003002  cmp     dword ptr [r8+0Ch], 46000000h
0x18000300a  jnz     short loc_180003029
0x18000300c  mov     rbx, [rdx+8]
0x180003010  add     rbx, r14
0x180003013  mov     rcx, rbx
0x180003016  mov     rax, [rbx]
0x180003019  mov     rax, [rax+8]
0x18000301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003022  xor     eax, eax
0x180003024  mov     [rsi], rbx
0x180003027  jmp     short loc_1800030A5
0x180003029  cmp     qword ptr [rdx+10h], 0
0x18000302e  jz      short loc_180003090
0x180003030  mov     rcx, [rbx]
0x180003033  test    rcx, rcx
0x180003036  jnz     short loc_18000303D
0x180003038  lea     ebp, [rcx+1]
0x18000303b  jmp     short loc_18000305D
0x18000303d  mov     eax, [rdi]
0x18000303f  cmp     [rcx], eax
0x180003041  jnz     short loc_180003085
0x180003043  mov     eax, [rdi+4]
0x180003046  cmp     [rcx+4], eax
0x180003049  jnz     short loc_180003085
0x18000304b  mov     eax, [rdi+8]
0x18000304e  cmp     [rcx+8], eax
0x180003051  jnz     short loc_180003085
0x180003053  mov     eax, [rdi+0Ch]
0x180003056  cmp     [rcx+0Ch], eax
0x180003059  jnz     short loc_180003085
0x18000305b  xor     ebp, ebp
0x18000305d  mov     rax, [rbx+10h]
0x180003061  cmp     rax, 1
0x180003065  jz      short loc_180003097
0x180003067  mov     r9, [rbx+8]
0x18000306b  mov     r8, rsi
0x18000306e  mov     rdx, rdi
0x180003071  mov     rcx, r14
0x180003074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003079  test    eax, eax
0x18000307b  jz      short loc_1800030A5
0x18000307d  test    ebp, ebp
0x18000307f  jnz     short loc_180003085
0x180003081  test    eax, eax
0x180003083  js      short loc_1800030A5
0x180003085  add     rbx, 18h
0x180003089  cmp     qword ptr [rbx+10h], 0
0x18000308e  jnz     short loc_180003030
0x180003090  mov     eax, 80004002h
0x180003095  jmp     short loc_1800030A5
0x180003097  mov     rbx, [rbx+8]
0x18000309b  jmp     loc_180003010
0x1800030a0  mov     eax, 80070057h
0x1800030a5  add     rsp, 30h
0x1800030a9  pop     r14
0x1800030ab  pop     rdi
0x1800030ac  pop     rsi
0x1800030ad  pop     rbp
0x1800030ae  pop     rbx
0x1800030af  retn
```
