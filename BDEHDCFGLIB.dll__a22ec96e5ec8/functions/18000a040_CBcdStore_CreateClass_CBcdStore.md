# CBcdStore::CreateClass(CBcdStore * *)

- ea: `0x18000a040`
- end: `0x18000a0e9`
- name: `?CreateClass@CBcdStore@@SAJPEAPEAV1@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct CBcdStore **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007bd0`

## callees

- `0x1800015c4`
- `0x180001c80`
- `0x18000a040`
- `0x18000a4f0`
- `0x18000bae0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CBcdStore::CreateClass(struct CBcdStore **a1)
{
  CBcdStore *v2; // rax
  CBcdWmiWrapper *v3; // rbx
  int v4; // edi

  *a1 = 0;
  v2 = (CBcdStore *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    v3 = CBcdStore::CBcdStore(v2);
  else
    v3 = 0;
  if ( v3 )
  {
    v4 = CBcdWmiWrapper::InitializeClass(v3, L"BcdStore");
    if ( v4 >= 0 )
    {
      *a1 = v3;
      v3 = 0;
    }
  }
  else
  {
    v4 = -2147024882;
  }
  if ( v3 )
    (**(void (__fastcall ***)(CBcdWmiWrapper *, __int64))v3)(v3, 1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a040  mov     [rsp+arg_0], rbx
0x18000a045  mov     [rsp+arg_8], rsi
0x18000a04a  push    rdi
0x18000a04b  sub     rsp, 30h
0x18000a04f  mov     rsi, rcx
0x18000a052  mov     [rsp+38h+var_10], 0
0x18000a05b  mov     qword ptr [rcx], 0
0x18000a062  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a069  mov     ecx, 28h ; '('; unsigned __int64
0x18000a06e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a073  test    rax, rax
0x18000a076  jz      short loc_18000A085
0x18000a078  mov     rcx, rax; this
0x18000a07b  call    ??0CBcdStore@@IEAA@XZ; CBcdStore::CBcdStore(void)
0x18000a080  mov     rbx, rax
0x18000a083  jmp     short loc_18000A087
0x18000a085  xor     ebx, ebx
0x18000a087  mov     [rsp+38h+var_10], rbx
0x18000a08c  test    rbx, rbx
0x18000a08f  jnz     short loc_18000A09C
0x18000a091  mov     edi, 8007000Eh
0x18000a096  mov     [rsp+38h+var_18], edi
0x18000a09a  jmp     short loc_18000A0BF
0x18000a09c  lea     rdx, aBcdstore; "BcdStore"
0x18000a0a3  mov     rcx, rbx; this
0x18000a0a6  call    ?InitializeClass@CBcdWmiWrapper@@IEAAJPEBG@Z; CBcdWmiWrapper::InitializeClass(ushort const *)
0x18000a0ab  mov     edi, eax
0x18000a0ad  mov     [rsp+38h+var_18], eax
0x18000a0b1  test    eax, eax
0x18000a0b3  js      short loc_18000A0BF
0x18000a0b5  mov     [rsi], rbx
0x18000a0b8  xor     ebx, ebx
0x18000a0ba  mov     [rsp+38h+var_10], rbx
0x18000a0bf  test    rbx, rbx
0x18000a0c2  jz      short loc_18000A0D7
0x18000a0c4  mov     rax, [rbx]
0x18000a0c7  mov     edx, 1
0x18000a0cc  mov     rcx, rbx
0x18000a0cf  mov     rax, [rax]
0x18000a0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d7  mov     eax, edi
0x18000a0d9  mov     rbx, [rsp+38h+arg_0]
0x18000a0de  mov     rsi, [rsp+38h+arg_8]
0x18000a0e3  add     rsp, 30h
0x18000a0e7  pop     rdi
0x18000a0e8  retn
0x180013a20  push    rbp
0x180013a22  sub     rsp, 20h
0x180013a26  mov     rbp, rdx
0x180013a29  mov     rcx, [rbp+28h]
0x180013a2d  test    rcx, rcx
0x180013a30  jz      short loc_180013A43
0x180013a32  mov     rax, [rcx]
0x180013a35  mov     edx, 1
0x180013a3a  mov     rax, [rax]
0x180013a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a42  nop
0x180013a43  add     rsp, 20h
0x180013a47  pop     rbp
0x180013a48  retn
```
