# NativeZLibDLLStub::InitDelegates

- ea: `0x5c750`
- end: `0x5c800`
- name: `NativeZLibDLLStub::InitDelegates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5c800`

## string_xrefs

- `0x5c7aa`: `zlibCompileFlags`

## pseudocode

```c

```

## disassembly

```asm
0x5c750  ldstr    aDeflateinit2// "deflateInit2_"
0x5c755  call     T0x2B00001D
0x5c75a  stsfld   class DeflateInit2_Delegate NativeZLibDLLStub::deflateInit2_Delegate
0x5c75f  ldstr    aDeflate// "deflate"
0x5c764  call     T0x2B00001E
0x5c769  stsfld   class DeflateDelegate NativeZLibDLLStub::deflateDelegate
0x5c76e  ldstr    aDeflateend// "deflateEnd"
0x5c773  call     T0x2B00001F
0x5c778  stsfld   class DeflateEndDelegate NativeZLibDLLStub::deflateEndDelegate
0x5c77d  ldstr    aInflateinit2// "inflateInit2_"
0x5c782  call     T0x2B000020
0x5c787  stsfld   class InflateInit2_Delegate NativeZLibDLLStub::inflateInit2_Delegate
0x5c78c  ldstr    aInflate// "inflate"
0x5c791  call     T0x2B000021
0x5c796  stsfld   class InflateDelegate NativeZLibDLLStub::inflateDelegate
0x5c79b  ldstr    aInflateend// "inflateEnd"
0x5c7a0  call     T0x2B000022
0x5c7a5  stsfld   class InflateEndDelegate NativeZLibDLLStub::inflateEndDelegate
0x5c7aa  ldstr    aZlibcompilefla// "zlibCompileFlags"
0x5c7af  call     T0x2B000023
0x5c7b4  stsfld   class ZlibCompileFlagsDelegate NativeZLibDLLStub::zlibCompileFlagsDelegate
0x5c7b9  ldsfld   class DeflateInit2_Delegate NativeZLibDLLStub::deflateInit2_Delegate
0x5c7be  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7c3  ldsfld   class DeflateDelegate NativeZLibDLLStub::deflateDelegate
0x5c7c8  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7cd  ldsfld   class DeflateEndDelegate NativeZLibDLLStub::deflateEndDelegate
0x5c7d2  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7d7  ldsfld   class InflateInit2_Delegate NativeZLibDLLStub::inflateInit2_Delegate
0x5c7dc  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7e1  ldsfld   class InflateDelegate NativeZLibDLLStub::inflateDelegate
0x5c7e6  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7eb  ldsfld   class InflateEndDelegate NativeZLibDLLStub::inflateEndDelegate
0x5c7f0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7f5  ldsfld   class ZlibCompileFlagsDelegate NativeZLibDLLStub::zlibCompileFlagsDelegate
0x5c7fa  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x5c7ff  ret
```
