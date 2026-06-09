# D3DXShader::CPreProcessor::LeaveCriticalSection(void)

- ea: `0x140098ab4`
- end: `0x140098b2f`
- name: `?LeaveCriticalSection@CPreProcessor@D3DXShader@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(D3DXShader::CPreProcessor *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14008bff0`
- `0x14008ca90`
- `0x14008d3c0`
- `0x140094d70`
- `0x14009564c`
- `0x140095bc8`

## callees

- `0x140098ab4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140098b1b`
- `KERNEL32!DeleteCriticalSection` at `0x140098b1b`
- `KERNEL32!LeaveCriticalSection` at `0x140098ad9`
- `KERNEL32!LeaveCriticalSection` at `0x140098ad9`
- `KERNEL32!Sleep` at `0x140098ae8`
- `KERNEL32!Sleep` at `0x140098ae8`

## pseudocode

```c
void __fastcall D3DXShader::CPreProcessor::LeaveCriticalSection(D3DXShader::CPreProcessor *this)
{
  D3DXCore::CAlloc *v1; // rax

  v1 = (D3DXCore::CAlloc *)*((_QWORD *)this + 159);
  *((_DWORD *)this + 316) = 0;
  D3DXShader::CNode::s_pAlloc = v1;
  LeaveCriticalSection(&D3DXShader::g_CriticalSection);
  while ( _InterlockedCompareExchange(&D3DXShader::g_SpinLock, 1, 0) == 1 )
    Sleep(1u);
  if ( !--D3DXShader::g_NumContenders )
    DeleteCriticalSection(&D3DXShader::g_CriticalSection);
  _InterlockedExchange(&D3DXShader::g_SpinLock, 0);
}

```

## disassembly

```asm
0x140098ab4  push    rbx
0x140098ab6  sub     rsp, 20h
0x140098aba  mov     rax, [rcx+4F8h]
0x140098ac1  mov     dword ptr [rcx+4F0h], 0
0x140098acb  lea     rcx, ?g_CriticalSection@D3DXShader@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140098ad2  mov     cs:?s_pAlloc@CNode@D3DXShader@@1PEAVCAlloc@D3DXCore@@EA, rax; D3DXCore::CAlloc * D3DXShader::CNode::s_pAlloc
0x140098ad9  call    cs:__imp_LeaveCriticalSection
0x140098adf  mov     ebx, 1
0x140098ae4  jmp     short loc_140098AEE
0x140098ae6  mov     ecx, ebx; dwMilliseconds
0x140098ae8  call    cs:__imp_Sleep
0x140098aee  xor     eax, eax
0x140098af0  lock cmpxchg cs:?g_SpinLock@D3DXShader@@3JC, ebx; long volatile D3DXShader::g_SpinLock
0x140098af8  cmp     eax, ebx
0x140098afa  jz      short loc_140098AE6
0x140098afc  mov     eax, cs:?g_NumContenders@D3DXShader@@3JC; long volatile D3DXShader::g_NumContenders
0x140098b02  sub     eax, ebx
0x140098b04  mov     cs:?g_NumContenders@D3DXShader@@3JC, eax; long volatile D3DXShader::g_NumContenders
0x140098b0a  mov     eax, cs:?g_NumContenders@D3DXShader@@3JC; long volatile D3DXShader::g_NumContenders
0x140098b10  test    eax, eax
0x140098b12  jnz     short loc_140098B21
0x140098b14  lea     rcx, ?g_CriticalSection@D3DXShader@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140098b1b  call    cs:__imp_DeleteCriticalSection
0x140098b21  xor     eax, eax
0x140098b23  xchg    eax, cs:?g_SpinLock@D3DXShader@@3JC; long volatile D3DXShader::g_SpinLock
0x140098b29  add     rsp, 20h
0x140098b2d  pop     rbx
0x140098b2e  retn
```
