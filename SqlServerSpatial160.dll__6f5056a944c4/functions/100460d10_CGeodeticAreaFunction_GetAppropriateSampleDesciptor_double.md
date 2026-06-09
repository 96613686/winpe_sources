# CGeodeticAreaFunction::GetAppropriateSampleDesciptor(double)

- ea: `0x100460d10`
- end: `0x100460d3b`
- name: `?GetAppropriateSampleDesciptor@CGeodeticAreaFunction@@EEBAAEBUSampleDescriptor@@N@Z`
- size: `43`
- prototype: `const struct SampleDescriptor *__fastcall(CGeodeticAreaFunction *__hidden this, double)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100460d10`

## pseudocode

```c
const struct SampleDescriptor *__fastcall CGeodeticAreaFunction::GetAppropriateSampleDesciptor(
        CGeodeticAreaFunction *this,
        double a2)
{
  const struct SampleDescriptor *result; // rax

  if ( a2 > 0.99904822 )
    return (const struct SampleDescriptor *)&SampleDescriptor_sample2;
  result = (const struct SampleDescriptor *)&SampleDescriptor_sample3;
  if ( a2 <= 0.9902680699999999 )
    return (const struct SampleDescriptor *)&SampleDescriptor_sample6;
  return result;
}

```

## disassembly

```asm
0x100460d10  comisd  xmm1, cs:__real@3feff833f900dd4b
0x100460d18  jbe     short loc_100460D22
0x100460d1a  lea     rax, ?SampleDescriptor_sample2@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample2
0x100460d21  retn
0x100460d22  comisd  xmm1, cs:__real@3fefb046a9dd8988
0x100460d2a  lea     rax, ?SampleDescriptor_sample3@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample3
0x100460d31  ja      short locret_100460D3A
0x100460d33  lea     rax, ?SampleDescriptor_sample6@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample6
0x100460d3a  retn
```
