# AsyncPipe::WriteCompletedCallback(void)

- ea: `0x14000ddf0`
- end: `0x14000ded8`
- name: `?WriteCompletedCallback@AsyncPipe@@AEAAXXZ`
- size: `232`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d6c0`

## callees

- `0x1400016c4`
- `0x140003594`
- `0x14000dbbc`
- `0x14000ddf0`
- `0x14000e1b4`
- `0x140012010`

## string_xrefs

- `0x14000de2f`: `WriteFile`

## pseudocode

```c
void __fastcall AsyncPipe::WriteCompletedCallback(PVOID pv)
{
  int v1; // r9d
  _QWORD *v2; // rbx
  void *v3; // rdi
  __int64 v4; // r9
  unsigned __int64 v5; // r10
  unsigned __int64 v6; // rax

  v1 = *((_DWORD *)pv + 63);
  v2 = pv;
  switch ( v1 )
  {
    case 0:
    case 109:
    case 232:
    case 233:
      goto LABEL_8;
    case 995:
      goto LABEL_15;
    case 1223:
LABEL_8:
      v3 = (void *)*((_QWORD *)pv + 183);
      if ( v3 )
      {
        std::vector<unsigned char>::~vector<unsigned char>(*((char ***)pv + 183));
        operator delete(v3);
      }
      v4 = v2[10];
      if ( !v4 )
      {
        v2[183] = 0;
        goto LABEL_16;
      }
      v5 = v2[9];
      v6 = v4 - 1;
      v2[183] = *(_QWORD *)(*(_QWORD *)(v2[7] + 8 * ((v2[8] - 1LL) & (v5 >> 1))) + 8 * (v5 & 1));
      v2[10] = v4 - 1;
      if ( v4 != 1 )
        v6 = v5 + 1;
      v2[9] = v6;
      pv = v2;
LABEL_15:
      AsyncPipe::StartWrite((char *)pv);
      goto LABEL_16;
  }
  __FatalError((const char *)pv, 583, "WriteFile", v1);
LABEL_16:
  (*(void (__fastcall **)(_QWORD *))(*v2 + 24LL))(v2);
}

```

## disassembly

```asm
0x14000ddf0  mov     [rsp+arg_0], rbx
0x14000ddf5  push    rdi
0x14000ddf6  sub     rsp, 20h
0x14000ddfa  mov     r9d, [rcx+0FCh]; unsigned int
0x14000de01  mov     rbx, rcx
0x14000de04  mov     edx, r9d
0x14000de07  test    r9d, r9d
0x14000de0a  jz      short loc_14000DE42
0x14000de0c  sub     edx, 6Dh ; 'm'
0x14000de0f  jz      short loc_14000DE42
0x14000de11  sub     edx, 7Bh ; '{'
0x14000de14  jz      short loc_14000DE42
0x14000de16  sub     edx, 1
0x14000de19  jz      short loc_14000DE42
0x14000de1b  sub     edx, 2FAh
0x14000de21  jz      loc_14000DEBA
0x14000de27  cmp     edx, 0E4h
0x14000de2d  jz      short loc_14000DE42
0x14000de2f  lea     r8, aWritefile; "WriteFile"
0x14000de36  mov     edx, 247h; unsigned int
0x14000de3b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000de40  jmp     short loc_14000DEBF
0x14000de42  mov     rdi, [rcx+5B8h]
0x14000de49  test    rdi, rdi
0x14000de4c  jz      short loc_14000DE63
0x14000de4e  mov     rcx, rdi
0x14000de51  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14000de56  mov     edx, 18h
0x14000de5b  mov     rcx, rdi; Block
0x14000de5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000de63  mov     r9, [rbx+50h]
0x14000de67  test    r9, r9
0x14000de6a  jnz     short loc_14000DE75
0x14000de6c  mov     [rbx+5B8h], r9
0x14000de73  jmp     short loc_14000DEBF
0x14000de75  mov     r10, [rbx+48h]
0x14000de79  mov     rax, [rbx+40h]
0x14000de7d  mov     rcx, r10
0x14000de80  dec     rax
0x14000de83  and     ecx, 1
0x14000de86  mov     rdx, r10
0x14000de89  shr     rdx, 1
0x14000de8c  and     rdx, rax
0x14000de8f  mov     rax, [rbx+38h]
0x14000de93  mov     rax, [rax+rdx*8]
0x14000de97  mov     rcx, [rax+rcx*8]
0x14000de9b  lea     rax, [r9-1]
0x14000de9f  mov     [rbx+5B8h], rcx
0x14000dea6  mov     [rbx+50h], rax
0x14000deaa  test    rax, rax
0x14000dead  jz      short loc_14000DEB3
0x14000deaf  lea     rax, [r10+1]
0x14000deb3  mov     [rbx+48h], rax
0x14000deb7  mov     rcx, rbx; pv
0x14000deba  call    ?StartWrite@AsyncPipe@@AEAAXXZ; AsyncPipe::StartWrite(void)
0x14000debf  mov     rax, [rbx]
0x14000dec2  mov     rcx, rbx
0x14000dec5  mov     rax, [rax+18h]
0x14000dec9  mov     rbx, [rsp+28h+arg_0]
0x14000dece  add     rsp, 20h
0x14000ded2  pop     rdi
0x14000ded3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
