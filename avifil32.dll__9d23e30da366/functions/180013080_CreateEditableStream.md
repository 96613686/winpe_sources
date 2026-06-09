# CreateEditableStream

- ea: `0x180013080`
- end: `0x180013140`
- name: `CreateEditableStream`
- size: `192`
- prototype: `HRESULT __stdcall(PAVISTREAM *ppsEditable, PAVISTREAM psSource)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001460`
- `0x180011f9c`
- `0x180013080`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall CreateEditableStream(PAVISTREAM *ppsEditable, PAVISTREAM psSource)
{
  struct IAVIStreamVtbl *lpVtbl; // rax
  struct CEditStream *v6; // rax
  IAVIStream *v7; // rax
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF

  if ( psSource
    && (lpVtbl = psSource->lpVtbl,
        v8 = 0,
        ((void (__fastcall *)(PAVISTREAM, GUID *, __int64 *))lpVtbl->QueryInterface)(psSource, &IID_IAVIEditStream, &v8),
        v8) )
  {
    (*(void (__fastcall **)(__int64, PAVISTREAM *))(*(_QWORD *)v8 + 48LL))(v8, ppsEditable);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return 0;
  }
  else
  {
    v6 = CEditStream::NewEditStream(psSource);
    if ( v6 )
    {
      v7 = (IAVIStream *)((char *)v6 + *(int *)(*(_QWORD *)v6 + 4LL));
      *ppsEditable = v7;
      return v7 == 0 ? 0x80044067 : 0;
    }
    else
    {
      *ppsEditable = 0;
      return -2147205017;
    }
  }
}

```

## disassembly

```asm
0x180013080  mov     [rsp+arg_10], rbx
0x180013085  push    rdi
0x180013086  sub     rsp, 30h
0x18001308a  mov     rax, cs:__security_cookie
0x180013091  xor     rax, rsp
0x180013094  mov     [rsp+38h+var_10], rax
0x180013099  mov     rbx, rdx
0x18001309c  mov     rdi, rcx
0x18001309f  test    rdx, rdx
0x1800130a2  jz      short loc_1800130F5
0x1800130a4  mov     rax, [rdx]
0x1800130a7  lea     r8, [rsp+38h+var_18]
0x1800130ac  lea     rdx, IID_IAVIEditStream
0x1800130b3  mov     [rsp+38h+var_18], 0
0x1800130bc  mov     rcx, rbx
0x1800130bf  mov     rax, [rax]
0x1800130c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130c7  mov     rcx, [rsp+38h+var_18]
0x1800130cc  test    rcx, rcx
0x1800130cf  jz      short loc_1800130F5
0x1800130d1  mov     rax, [rcx]
0x1800130d4  mov     rdx, rdi
0x1800130d7  mov     rax, [rax+30h]
0x1800130db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130e0  mov     rcx, [rsp+38h+var_18]
0x1800130e5  mov     rax, [rcx]
0x1800130e8  mov     rax, [rax+10h]
0x1800130ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130f1  xor     eax, eax
0x1800130f3  jmp     short loc_180013128
0x1800130f5  mov     rcx, rbx; struct IAVIStream *
0x1800130f8  call    ?NewEditStream@CEditStream@@SAPEAV1@PEAUIAVIStream@@@Z; CEditStream::NewEditStream(IAVIStream *)
0x1800130fd  mov     rdx, rax
0x180013100  test    rax, rax
0x180013103  jnz     short loc_18001310F
0x180013105  mov     [rdi], rax
0x180013108  mov     eax, 80044067h
0x18001310d  jmp     short loc_180013128
0x18001310f  mov     rax, [rax]
0x180013112  movsxd  rax, dword ptr [rax+4]
0x180013116  add     rax, rdx
0x180013119  mov     [rdi], rax
0x18001311c  neg     rax
0x18001311f  sbb     eax, eax
0x180013121  not     eax
0x180013123  and     eax, 80044067h
0x180013128  mov     rcx, [rsp+38h+var_10]
0x18001312d  xor     rcx, rsp; StackCookie
0x180013130  call    __security_check_cookie
0x180013135  mov     rbx, [rsp+38h+arg_10]
0x18001313a  add     rsp, 30h
0x18001313e  pop     rdi
0x18001313f  retn
```
