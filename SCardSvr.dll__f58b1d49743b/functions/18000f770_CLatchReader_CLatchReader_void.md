# CLatchReader::~CLatchReader(void)

- ea: `0x18000f770`
- end: `0x18000f7f9`
- name: `??1CLatchReader@@QEAA@XZ`
- size: `137`
- prototype: `void __fastcall(CReader **this)`
- caller_count: `26`
- callee_count: `6`
- tags: ``

## callers

- `0x180001950`
- `0x1800039e0`
- `0x180004c8c`
- `0x180005af0`
- `0x18000f2a0`
- `0x180018d4c`
- `0x18002c070`
- `0x18002d0c0`
- `0x18002d870`
- `0x18002dcc4`
- `0x18002f890`
- `0x18002fa94`
- `0x18002fcf0`
- `0x18003291d`
- `0x180032953`
- `0x1800329ad`
- `0x180032c90`
- `0x1800332a2`
- `0x180033312`
- `0x180034170`
- `0x180034240`
- `0x180034f82`
- `0x180035c56`
- `0x180035fb7`
- `0x180036066`
- `0x180036354`

## callees

- `0x180006ad0`
- `0x18000d9c0`
- `0x18000f770`
- `0x18000f800`
- `0x180010670`
- `0x180010af0`

## pseudocode

```c
void __fastcall CLatchReader::~CLatchReader(CReader **this)
{
  CReader *v2; // rcx
  CReader *v3; // rdi
  char v4; // bl

  v2 = *this;
  if ( v2 )
  {
    if ( !(unsigned int)CReader::InitFailed(v2) )
    {
      CMutex::Share((CReader *)((char *)*this + 328));
      v3 = *this;
      v4 = *((_BYTE *)this + 12);
      CMutex::Share((CReader *)((char *)v3 + 240));
      if ( v4 )
      {
        if ( (unsigned int)CMutex::IsGrabbed((CReader *)((char *)v3 + 240)) )
          CReader::TransactionTimeoutStart(v3);
        else
          CReader::TransactionTimeoutStop(v3);
      }
    }
  }
}

```

## disassembly

```asm
0x18000f770  mov     [rsp+arg_0], rbx
0x18000f775  mov     [rsp+arg_8], rsi
0x18000f77a  push    rdi
0x18000f77b  sub     rsp, 20h
0x18000f77f  mov     rbx, rcx
0x18000f782  mov     rcx, [rcx]; this
0x18000f785  test    rcx, rcx
0x18000f788  jz      short loc_18000F7B9
0x18000f78a  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x18000f78f  test    eax, eax
0x18000f791  jnz     short loc_18000F7B9
0x18000f793  mov     rcx, [rbx]
0x18000f796  add     rcx, 148h; this
0x18000f79d  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18000f7a2  mov     rdi, [rbx]
0x18000f7a5  movzx   ebx, byte ptr [rbx+0Ch]
0x18000f7a9  lea     rcx, [rdi+0F0h]; this
0x18000f7b0  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18000f7b5  test    bl, bl
0x18000f7b7  jnz     short loc_18000F7C9
0x18000f7b9  mov     rbx, [rsp+28h+arg_0]
0x18000f7be  mov     rsi, [rsp+28h+arg_8]
0x18000f7c3  add     rsp, 20h
0x18000f7c7  pop     rdi
0x18000f7c8  retn
0x18000f7c9  lea     rcx, [rdi+0F0h]; this
0x18000f7d0  call    ?IsGrabbed@CMutex@@QEAAHXZ; CMutex::IsGrabbed(void)
0x18000f7d5  mov     rcx, rdi; this
0x18000f7d8  test    eax, eax
0x18000f7da  jnz     short loc_18000F7F2
0x18000f7dc  call    ?TransactionTimeoutStop@CReader@@IEAAXXZ; CReader::TransactionTimeoutStop(void)
0x18000f7e1  nop
0x18000f7e2  mov     rbx, [rsp+28h+arg_0]
0x18000f7e7  mov     rsi, [rsp+28h+arg_8]
0x18000f7ec  add     rsp, 20h
0x18000f7f0  pop     rdi
0x18000f7f1  retn
0x18000f7f2  call    ?TransactionTimeoutStart@CReader@@IEAAXXZ; CReader::TransactionTimeoutStart(void)
0x18000f7f7  jmp     short loc_18000F7B9
```
