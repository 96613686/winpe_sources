# Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledFallback

- ea: `0x1400075a4`
- end: `0x1400075ba`
- name: `Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledFallback`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007568`

## callees

- `0x140008bd0`

## pseudocode

```c
__int64 __fastcall Feature_Mbbcx_Fix_Ip_Configuration_After_Disconnect__private_IsEnabledFallback(
        __int64 a1,
        __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, wil_details_featureDescriptors_a);
}

```

## disassembly

```asm
0x1400075a4  sub     rsp, 28h
0x1400075a8  lea     r8, wil_details_featureDescriptors_a
0x1400075af  call    wil_details_IsEnabledFallback
0x1400075b4  add     rsp, 28h
0x1400075b8  retn
```
