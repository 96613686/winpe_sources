# CALRPC_CONTEXT_SERIAL_rundown

- ea: `0x18002fdf0`
- end: `0x18002fe61`
- name: `CALRPC_CONTEXT_SERIAL_rundown`
- size: `113`
- prototype: `__int64 __fastcall(CServiceThread *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fde0`

## callees

- `0x1800059c0`
- `0x180006004`
- `0x180012380`
- `0x1800123a0`
- `0x180014c20`
- `0x18002fdf0`

## pseudocode

```c
void __fastcall CALRPC_CONTEXT_SERIAL_rundown(LPVOID *this)
{
  const unsigned __int8 *v2; // r8
  const unsigned __int8 *v3; // r9
  unsigned int i; // edx
  __int64 v5; // rax
  char v6; // [rsp+30h] [rbp+8h] BYREF

  CalRpcSetServiceThreadId(this);
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v6, qword_18004BA60, v2, v3);
  for ( i = 0; i < HIDWORD(qword_18004B0A8); ++i )
  {
    v5 = *((_QWORD *)Block + (int)i);
    if ( v5 && this[9] == *(LPVOID *)(v5 + 72) )
    {
      CDynamicArray<CServiceThread>::Set(HIDWORD(qword_18004B0A8), i, 0);
      break;
    }
  }
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v6);
  if ( this )
    CServiceThread::`scalar deleting destructor'((CServiceThread *)this);
}

```

## disassembly

```asm
0x18002fdf0  push    rbx
0x18002fdf2  sub     rsp, 20h
0x18002fdf6  mov     rbx, rcx
0x18002fdf9  call    ?CalRpcSetServiceThreadId@@YAKPEAVCServiceThread@@@Z; CalRpcSetServiceThreadId(CServiceThread *)
0x18002fdfe  mov     rdx, cs:qword_18004BA60; struct CCriticalSectionObject *
0x18002fe05  lea     rcx, [rsp+28h+arg_0]; this
0x18002fe0a  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002fe0f  mov     r8, cs:Block
0x18002fe16  xor     edx, edx
0x18002fe18  mov     ecx, dword ptr cs:qword_18004B0A8+4
0x18002fe1e  cmp     edx, ecx
0x18002fe20  jnb     short loc_18002FE44
0x18002fe22  movsxd  rax, edx
0x18002fe25  mov     rax, [r8+rax*8]
0x18002fe29  test    rax, rax
0x18002fe2c  jz      short loc_18002FE38
0x18002fe2e  mov     rax, [rax+48h]
0x18002fe32  cmp     [rbx+48h], rax
0x18002fe36  jz      short loc_18002FE3C
0x18002fe38  inc     edx
0x18002fe3a  jmp     short loc_18002FE1E
0x18002fe3c  xor     r8d, r8d
0x18002fe3f  call    ?Set@?$CDynamicArray@VCServiceThread@@@@QEAAPEAVCServiceThread@@HPEAV2@@Z; CDynamicArray<CServiceThread>::Set(int,CServiceThread *)
0x18002fe44  lea     rcx, [rsp+28h+arg_0]; this
0x18002fe49  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002fe4e  test    rbx, rbx
0x18002fe51  jz      short loc_18002FE5B
0x18002fe53  mov     rcx, rbx; this
0x18002fe56  call    ??_GCServiceThread@@QEAAPEAXI@Z; CServiceThread::`scalar deleting destructor'(uint)
0x18002fe5b  add     rsp, 20h
0x18002fe5f  pop     rbx
0x18002fe60  retn
```
