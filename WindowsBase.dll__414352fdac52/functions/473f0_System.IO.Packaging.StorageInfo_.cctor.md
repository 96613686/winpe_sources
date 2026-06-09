# System.IO.Packaging.StorageInfo::.cctor

- ea: `0x473f0`
- end: `0x4740f`
- name: `System.IO.Packaging.StorageInfo::.cctor`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x473f0`: `CompressionTransform`
- `0x473fa`: `NoEncryptionNormalCompression`
- `0x47404`: `RMEncryptionNormalCompression`

## pseudocode

```c

```

## disassembly

```asm
0x473f0  ldstr    aCompressiontra// "CompressionTransform"
0x473f5  stsfld   string System.IO.Packaging.StorageInfo::sc_compressionTransformName
0x473fa  ldstr    aNoencryptionno// "NoEncryptionNormalCompression"
0x473ff  stsfld   string System.IO.Packaging.StorageInfo::sc_dataspaceLabelNoEncryptionNormalCompression
0x47404  ldstr    aRmencryptionno// "RMEncryptionNormalCompression"
0x47409  stsfld   string System.IO.Packaging.StorageInfo::sc_dataspaceLabelRMEncryptionNormalCompression
0x4740e  ret
```
