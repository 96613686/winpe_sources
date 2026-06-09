# Microsoft::WRL::ComPtr<PidlEnum>::~ComPtr<PidlEnum>(void)

- ea: `0x180014b04`
- end: `0x180014b24`
- name: `??1?$ComPtr@VPidlEnum@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800187af`

## callees

- `0x180009a90`
- `0x180014b04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::ComPtr<PidlEnum>::~ComPtr<PidlEnum>(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumIDList>::Release(
             result,
             a2,
             a3);
  }
  return result;
}

```

## disassembly

```asm
0x180014b04  sub     rsp, 28h
0x180014b08  mov     rax, [rcx]
0x180014b0b  test    rax, rax
0x180014b0e  jz      short loc_180014B1F
0x180014b10  mov     qword ptr [rcx], 0
0x180014b17  mov     rcx, rax
0x180014b1a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEnumIDList@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumIDList>::Release(void)
0x180014b1f  add     rsp, 28h
0x180014b23  retn
```
