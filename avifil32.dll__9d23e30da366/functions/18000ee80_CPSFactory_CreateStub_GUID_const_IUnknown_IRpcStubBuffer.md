# CPSFactory::CreateStub(_GUID const &,IUnknown *,IRpcStubBuffer * *)

- ea: `0x18000ee80`
- end: `0x18000ef5b`
- name: `?CreateStub@CPSFactory@@UEAAJAEBU_GUID@@PEAUIUnknown@@PEAPEAUIRpcStubBuffer@@@Z`
- size: `219`
- prototype: `int(CPSFactory *__hidden this, const struct _GUID *, struct IUnknown *, struct IRpcStubBuffer **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x18000eb90`
- `0x18000ec20`
- `0x18000ee80`
- `0x1800102b8`
- `0x180010400`

## pseudocode

```c
__int64 __fastcall CPSFactory::CreateStub(
        CPSFactory *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        struct IRpcStubBuffer **a4)
{
  struct IRpcStubBuffer *v7; // rbx
  unsigned int v8; // edi

  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IAVIStream )
    return CStubAVIStream::Create(a3, a4);
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAVIFile.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAVIFile.Data4 )
  {
    *a4 = 0;
    v7 = (struct IRpcStubBuffer *)operator new(0x18u);
    if ( v7 )
    {
      ++uUseCount;
      v7->lpVtbl = (struct IRpcStubBufferVtbl *)&CStubAVIFile::`vftable';
      LODWORD(v7[1].lpVtbl) = 1;
      v7[2].lpVtbl = 0;
      RegisterStubUsage();
      v8 = CStubAVIFile::Connect((CStubAVIFile *)v7, a3);
      if ( v8 )
      {
        CStubAVIFile::Release((CStubAVIFile *)v7);
      }
      else
      {
        *a4 = v7;
        return 0;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return v8;
  }
  else
  {
    *a4 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x18000ee80  mov     [rsp+arg_0], rbx
0x18000ee85  mov     [rsp+arg_8], rsi
0x18000ee8a  push    rdi
0x18000ee8b  sub     rsp, 20h
0x18000ee8f  mov     rax, [rdx]
0x18000ee92  mov     rsi, r9
0x18000ee95  cmp     rax, qword ptr cs:IID_IAVIStream.Data1
0x18000ee9c  mov     rdi, r8
0x18000ee9f  jnz     short loc_18000EEBE
0x18000eea1  mov     rax, [rdx+8]
0x18000eea5  cmp     rax, qword ptr cs:IID_IAVIStream.Data4
0x18000eeac  jnz     short loc_18000EEBE
0x18000eeae  mov     rdx, r9; struct IRpcStubBuffer **
0x18000eeb1  mov     rcx, r8; struct IUnknown *
0x18000eeb4  call    ?Create@CStubAVIStream@@SAJPEAUIUnknown@@PEAPEAUIRpcStubBuffer@@@Z; CStubAVIStream::Create(IUnknown *,IRpcStubBuffer * *)
0x18000eeb9  jmp     loc_18000EF4B
0x18000eebe  mov     rax, [rdx]
0x18000eec1  cmp     rax, qword ptr cs:IID_IAVIFile.Data1
0x18000eec8  jnz     short loc_18000EF3F
0x18000eeca  mov     rax, [rdx+8]
0x18000eece  cmp     rax, qword ptr cs:IID_IAVIFile.Data4
0x18000eed5  jnz     short loc_18000EF3F
0x18000eed7  mov     ecx, 18h; Size
0x18000eedc  mov     qword ptr [r9], 0
0x18000eee3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eee8  mov     rbx, rax
0x18000eeeb  test    rax, rax
0x18000eeee  jz      short loc_18000EF36
0x18000eef0  inc     cs:uUseCount
0x18000eef6  lea     rax, ??_7CStubAVIFile@@6B@; const CStubAVIFile::`vftable'
0x18000eefd  mov     [rbx], rax
0x18000ef00  mov     dword ptr [rbx+8], 1
0x18000ef07  mov     qword ptr [rbx+10h], 0
0x18000ef0f  call    ?RegisterStubUsage@@YAXXZ; RegisterStubUsage(void)
0x18000ef14  mov     rdx, rdi; struct IUnknown *
0x18000ef17  mov     rcx, rbx; this
0x18000ef1a  call    ?Connect@CStubAVIFile@@UEAAJPEAUIUnknown@@@Z; CStubAVIFile::Connect(IUnknown *)
0x18000ef1f  mov     edi, eax
0x18000ef21  test    eax, eax
0x18000ef23  jz      short loc_18000EF2F
0x18000ef25  mov     rcx, rbx; this
0x18000ef28  call    ?Release@CStubAVIFile@@UEAAKXZ; CStubAVIFile::Release(void)
0x18000ef2d  jmp     short loc_18000EF3B
0x18000ef2f  mov     [rsi], rbx
0x18000ef32  xor     edi, edi
0x18000ef34  jmp     short loc_18000EF3B
0x18000ef36  mov     edi, 8007000Eh
0x18000ef3b  mov     eax, edi
0x18000ef3d  jmp     short loc_18000EF4B
0x18000ef3f  mov     qword ptr [r9], 0
0x18000ef46  mov     eax, 80004002h
0x18000ef4b  mov     rbx, [rsp+28h+arg_0]
0x18000ef50  mov     rsi, [rsp+28h+arg_8]
0x18000ef55  add     rsp, 20h
0x18000ef59  pop     rdi
0x18000ef5a  retn
```
