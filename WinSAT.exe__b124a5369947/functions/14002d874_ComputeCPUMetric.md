# ComputeCPUMetric

- ea: `0x14002d874`
- end: `0x14002d99d`
- name: `ComputeCPUMetric`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033bf4`

## callees

- `0x14002d874`
- `0x14002fc4c`

## string_xrefs

- `0x14002d884`: `/WinSAT/CPUCompressionAssessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond`
- `0x14002d8a2`: `/WinSAT/CPUEncryptionAssessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond`
- `0x14002d8c0`: `/WinSAT/CPUCompression2Assessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond`
- `0x14002d8de`: `/WinSAT/CPUEncryption2Assessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond`
- `0x14002d8fc`: `/WinSAT/CPUCRC32Assessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond`
- `0x14002d91a`: `/WinSAT/CPUCompressionAssessment[MaxThreads='1']/TotalBytesPerSecond`
- `0x14002d934`: `/WinSAT/CPUEncryptionAssessment[MaxThreads='1']/TotalBytesPerSecond`
- `0x14002d94e`: `/WinSAT/CPUCompression2Assessment[MaxThreads='1']/TotalBytesPerSecond`
- `0x14002d968`: `/WinSAT/CPUEncryption2Assessment[MaxThreads='1']/TotalBytesPerSecond`
- `0x14002d982`: `/WinSAT/CPUCRC32Assessment[MaxThreads='1']/TotalBytesPerSecond`

## pseudocode

```c
__int64 __fastcall ComputeCPUMetric(__int64 a1)
{
  __int64 result; // rax
  int v3; // eax
  unsigned int v4; // ecx

  result = ComputeSingleCPUMetric(
             a1,
             L"/WinSAT/CPUCompressionAssessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond",
             &dbl_140168968);
  if ( (int)result >= 0 )
  {
    result = ComputeSingleCPUMetric(
               a1,
               L"/WinSAT/CPUEncryptionAssessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond",
               &dbl_140168920);
    if ( (int)result >= 0 )
    {
      result = ComputeSingleCPUMetric(
                 a1,
                 L"/WinSAT/CPUCompression2Assessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond",
                 &dbl_140168918);
      if ( (int)result >= 0 )
      {
        result = ComputeSingleCPUMetric(
                   a1,
                   L"/WinSAT/CPUEncryption2Assessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond",
                   &dbl_140168928);
        if ( (int)result >= 0 )
        {
          result = ComputeSingleCPUMetric(
                     a1,
                     L"/WinSAT/CPUCRC32Assessment[MaxThreads='NumberOfSchedulableUnits']/TotalBytesPerSecond",
                     &qword_1401688A8);
          if ( (int)result >= 0 )
          {
            result = ComputeSingleCPUMetric(
                       a1,
                       L"/WinSAT/CPUCompressionAssessment[MaxThreads='1']/TotalBytesPerSecond",
                       &dbl_140168990);
            if ( (int)result >= 0 )
            {
              result = ComputeSingleCPUMetric(
                         a1,
                         L"/WinSAT/CPUEncryptionAssessment[MaxThreads='1']/TotalBytesPerSecond",
                         &dbl_1401688B0);
              if ( (int)result >= 0 )
              {
                result = ComputeSingleCPUMetric(
                           a1,
                           L"/WinSAT/CPUCompression2Assessment[MaxThreads='1']/TotalBytesPerSecond",
                           &dbl_1401688B8);
                if ( (int)result >= 0 )
                {
                  result = ComputeSingleCPUMetric(
                             a1,
                             L"/WinSAT/CPUEncryption2Assessment[MaxThreads='1']/TotalBytesPerSecond",
                             &dbl_140168988);
                  if ( (int)result >= 0 )
                  {
                    v3 = ComputeSingleCPUMetric(
                           a1,
                           L"/WinSAT/CPUCRC32Assessment[MaxThreads='1']/TotalBytesPerSecond",
                           &qword_1401688D8);
                    v4 = 0;
                    if ( v3 < 0 )
                      return (unsigned int)v3;
                    return v4;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002d874  push    rbx
0x14002d876  sub     rsp, 20h
0x14002d87a  lea     r8, dbl_140168968
0x14002d881  mov     rbx, rcx
0x14002d884  lea     rdx, aWinsatCpucompr_4; "/WinSAT/CPUCompressionAssessment[MaxThr"...
0x14002d88b  call    ComputeSingleCPUMetric
0x14002d890  test    eax, eax
0x14002d892  js      loc_14002D997
0x14002d898  lea     r8, dbl_140168920
0x14002d89f  mov     rcx, rbx
0x14002d8a2  lea     rdx, aWinsatCpuencry_5; "/WinSAT/CPUEncryptionAssessment[MaxThre"...
0x14002d8a9  call    ComputeSingleCPUMetric
0x14002d8ae  test    eax, eax
0x14002d8b0  js      loc_14002D997
0x14002d8b6  lea     r8, dbl_140168918
0x14002d8bd  mov     rcx, rbx
0x14002d8c0  lea     rdx, aWinsatCpucompr_1; "/WinSAT/CPUCompression2Assessment[MaxTh"...
0x14002d8c7  call    ComputeSingleCPUMetric
0x14002d8cc  test    eax, eax
0x14002d8ce  js      loc_14002D997
0x14002d8d4  lea     r8, dbl_140168928
0x14002d8db  mov     rcx, rbx
0x14002d8de  lea     rdx, aWinsatCpuencry_6; "/WinSAT/CPUEncryption2Assessment[MaxThr"...
0x14002d8e5  call    ComputeSingleCPUMetric
0x14002d8ea  test    eax, eax
0x14002d8ec  js      loc_14002D997
0x14002d8f2  lea     r8, qword_1401688A8
0x14002d8f9  mov     rcx, rbx
0x14002d8fc  lea     rdx, aWinsatCpucrc32; "/WinSAT/CPUCRC32Assessment[MaxThreads='"...
0x14002d903  call    ComputeSingleCPUMetric
0x14002d908  test    eax, eax
0x14002d90a  js      loc_14002D997
0x14002d910  lea     r8, dbl_140168990
0x14002d917  mov     rcx, rbx
0x14002d91a  lea     rdx, aWinsatCpucompr_2; "/WinSAT/CPUCompressionAssessment[MaxThr"...
0x14002d921  call    ComputeSingleCPUMetric
0x14002d926  test    eax, eax
0x14002d928  js      short loc_14002D997
0x14002d92a  lea     r8, dbl_1401688B0
0x14002d931  mov     rcx, rbx
0x14002d934  lea     rdx, aWinsatCpuencry_2; "/WinSAT/CPUEncryptionAssessment[MaxThre"...
0x14002d93b  call    ComputeSingleCPUMetric
0x14002d940  test    eax, eax
0x14002d942  js      short loc_14002D997
0x14002d944  lea     r8, dbl_1401688B8
0x14002d94b  mov     rcx, rbx
0x14002d94e  lea     rdx, aWinsatCpucompr_3; "/WinSAT/CPUCompression2Assessment[MaxTh"...
0x14002d955  call    ComputeSingleCPUMetric
0x14002d95a  test    eax, eax
0x14002d95c  js      short loc_14002D997
0x14002d95e  lea     r8, dbl_140168988
0x14002d965  mov     rcx, rbx
0x14002d968  lea     rdx, aWinsatCpuencry; "/WinSAT/CPUEncryption2Assessment[MaxThr"...
0x14002d96f  call    ComputeSingleCPUMetric
0x14002d974  test    eax, eax
0x14002d976  js      short loc_14002D997
0x14002d978  lea     r8, qword_1401688D8
0x14002d97f  mov     rcx, rbx
0x14002d982  lea     rdx, aWinsatCpucrc32_0; "/WinSAT/CPUCRC32Assessment[MaxThreads='"...
0x14002d989  call    ComputeSingleCPUMetric
0x14002d98e  xor     ecx, ecx
0x14002d990  test    eax, eax
0x14002d992  cmovs   ecx, eax
0x14002d995  mov     eax, ecx
0x14002d997  add     rsp, 20h
0x14002d99b  pop     rbx
0x14002d99c  retn
```
