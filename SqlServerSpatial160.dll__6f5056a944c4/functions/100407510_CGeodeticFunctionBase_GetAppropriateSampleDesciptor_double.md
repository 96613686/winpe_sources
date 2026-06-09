# CGeodeticFunctionBase::GetAppropriateSampleDesciptor(double)

- ea: `0x100407510`
- end: `0x10040754d`
- name: `?GetAppropriateSampleDesciptor@CGeodeticFunctionBase@@UEBAAEBUSampleDescriptor@@N@Z`
- size: `61`
- prototype: `const struct SampleDescriptor *__fastcall(CGeodeticFunctionBase *__hidden this, double)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100407510`

## pseudocode

```c
const struct SampleDescriptor *__fastcall CGeodeticFunctionBase::GetAppropriateSampleDesciptor(
        CGeodeticFunctionBase *this,
        double a2)
{
  const struct SampleDescriptor *result; // rax

  if ( a2 > 0.99999961922825 )
    return (const struct SampleDescriptor *)&SampleDescriptor_sample1;
  if ( a2 > 0.99813479842 )
    return (const struct SampleDescriptor *)&SampleDescriptor_sample2;
  result = (const struct SampleDescriptor *)&SampleDescriptor_sample3;
  if ( a2 <= 0.9848077 )
    return (const struct SampleDescriptor *)&SampleDescriptor_sample6;
  return result;
}

```

## disassembly

```asm
0x100407510  comisd  xmm1, cs:__real@3fefffff33932111
0x100407518  jbe     short loc_100407522
0x10040751a  lea     rax, ?SampleDescriptor_sample1@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample1
0x100407521  retn
0x100407522  comisd  xmm1, cs:__real@3feff0b86386d49a
0x10040752a  jbe     short loc_100407534
0x10040752c  lea     rax, ?SampleDescriptor_sample2@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample2
0x100407533  retn
0x100407534  comisd  xmm1, cs:__real@3fef838b700b2ad6
0x10040753c  lea     rax, ?SampleDescriptor_sample3@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample3
0x100407543  ja      short locret_10040754C
0x100407545  lea     rax, ?SampleDescriptor_sample6@@3USampleDescriptor@@B; SampleDescriptor const SampleDescriptor_sample6
0x10040754c  retn
```
