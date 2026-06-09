# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::.cctor

- ea: `0x4990`
- end: `0x4c5e`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::.cctor`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x4c60`

## string_xrefs

- `0x4b35`: `jpg, jpeg, jpe, wav, bmp, img, gif, json, mp4, web, png`
- `0x4b59`: `*,*.xml,*.xsd,*.xsl,*.png,*.gif,*.jpg,*.tif,*.jpeg,*.tiff,*.bmp,*.pdf,*.svg,*.rtf,*.txt,*.doc,*.docx,*.pps,*.ppt,*.pptx,*.rsmobile`
- `0x4b6b`: `text/html,application/xhtml+xml,image/svg+xml`
- `0x4bc4`: `https://app.powerbi.com/`
- `0x4c3d`: `GET, PUT, POST, PATCH, DELETE`

## pseudocode

```c

```

## disassembly

```asm
0x4990  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x4995  dup
0x4996  ldc.i4.2
0x4997  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x499c  ldstr    a5// "5"
0x49a1  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x49a6  dup
0x49a7  ldc.i4.3
0x49a8  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x49ad  ldstr    a7200// "7200"
0x49b2  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x49b7  dup
0x49b8  ldc.i4.5
0x49b9  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x49be  ldstr    a60// "60"
0x49c3  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x49c8  dup
0x49c9  ldc.i4.6
0x49ca  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x49cf  ldstr    aNormal// "Normal"
0x49d4  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x49d9  dup
0x49da  ldc.i4.7
0x49db  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x49e0  ldstr    a600// "600"
0x49e5  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x49ea  dup
0x49eb  ldc.i4.8
0x49ec  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x49f1  ldstr    a30// "30"
0x49f6  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x49fb  dup
0x49fc  ldc.i4.s 0xB
0x49fe  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a03  ldstr    a1000// "1000"
0x4a08  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a0d  dup
0x4a0e  ldc.i4.s 0xC
0x4a10  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a15  ldstr    a15// "15"
0x4a1a  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a1f  dup
0x4a20  ldc.i4.s 0xD
0x4a22  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a27  ldstr    a60// "60"
0x4a2c  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a31  dup
0x4a32  ldc.i4.s 0xE
0x4a34  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a39  ldstr    aMyReports// "My Reports"
0x4a3e  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a43  dup
0x4a44  ldc.i4.s 0xF
0x4a46  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a4b  ldstr    a300// "300"
0x4a50  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a55  dup
0x4a56  ldc.i4.s 0x11
0x4a58  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a5d  ldstr    a1800// "1800"
0x4a62  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a67  dup
0x4a68  ldc.i4.s 0x12
0x4a6a  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a6f  ldstr    a120// "120"
0x4a74  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a79  dup
0x4a7a  ldc.i4.s 0x13
0x4a7c  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a81  ldstr    a600// "600"
0x4a86  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a8b  dup
0x4a8c  ldc.i4.s 0x14
0x4a8e  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4a93  ldstr    aTrue// "true"
0x4a98  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4a9d  dup
0x4a9e  ldc.i4.s 0x15
0x4aa0  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4aa5  ldstr    aDefault// "Default"
0x4aaa  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4aaf  dup
0x4ab0  ldc.i4.s 0x16
0x4ab2  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4ab7  ldstr    aSql// "SQL"
0x4abc  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4ac1  dup
0x4ac2  ldc.i4.s 0x17
0x4ac4  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4ac9  ldstr    a180// "180"
0x4ace  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4ad3  dup
0x4ad4  ldc.i4.s 0x18
0x4ad6  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4adb  ldstr    a1500// "1500"
0x4ae0  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4ae5  dup
0x4ae6  ldc.i4.s 0x1A
0x4ae8  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4aed  ldstr    a1800// "1800"
0x4af2  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4af7  dup
0x4af8  ldc.i4.s 0x1B
0x4afa  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4aff  ldstr    a1// "-1"
0x4b04  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b09  dup
0x4b0a  ldc.i4.s 0x1D
0x4b0c  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b11  ldstr    aTrue_0// "True"
0x4b16  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b1b  dup
0x4b1c  ldc.i4.s 0x1E
0x4b1e  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b23  ldstr    a60// "60"
0x4b28  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b2d  dup
0x4b2e  ldc.i4.s 0x1C
0x4b30  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b35  ldstr    aJpgJpegJpeWavB// "jpg, jpeg, jpe, wav, bmp, img, gif, jso"...
0x4b3a  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b3f  dup
0x4b40  ldc.i4.s 0x1F
0x4b42  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b47  ldstr    aHttpHttpsMailt// "http,https,mailto"
0x4b4c  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b51  dup
0x4b52  ldc.i4.s 0x20
0x4b54  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b59  ldstr    aXmlXsdXslPngGi// "*,*.xml,*.xsd,*.xsl,*.png,*.gif,*.jpg,*"...
0x4b5e  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b63  dup
0x4b64  ldc.i4.s 0x21
0x4b66  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b6b  ldstr    aTextHtmlApplic// "text/html,application/xhtml+xml,image/s"...
0x4b70  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b75  dup
0x4b76  ldc.i4.1
0x4b77  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b7c  ldstr    aCustomheadersH// "<CustomHeaders> <Header> <Name>X-Frame-"...
0x4b81  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b86  dup
0x4b87  ldc.i4.s 0x22
0x4b89  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4b8e  ldstr    asc_7C08// ""
0x4b93  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4b98  dup
0x4b99  ldc.i4.s 0x23
0x4b9b  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4ba0  ldstr    asc_7C08// ""
0x4ba5  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4baa  dup
0x4bab  ldc.i4.s 0x24
0x4bad  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4bb2  ldstr    aTrue// "true"
0x4bb7  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4bbc  dup
0x4bbd  ldc.i4.s 0x25
0x4bbf  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4bc4  ldstr    aHttpsAppPowerb// "https://app.powerbi.com/"
0x4bc9  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4bce  dup
0x4bcf  ldc.i4.s 0x26
0x4bd1  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4bd6  ldstr    a100// "100"
0x4bdb  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4be0  dup
0x4be1  ldc.i4.s 0x27
0x4be3  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x4be8  ldstr    aFoldersKpisPag// "folders,kpis,paginatedreports,powerbire"...
0x4bed  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4bf2  dup
0x4bf3  ldc.i4.0
0x4bf4  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x4bf9  ldstr    asc_7C08// ""
0x4bfe  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4c03  dup
0x4c04  ldc.i4.1
0x4c05  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x4c0a  ldstr    aFalse// "false"
0x4c0f  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4c14  dup
0x4c15  ldc.i4.2
0x4c16  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x4c1b  ldstr    asc_7C08// ""
0x4c20  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4c25  dup
0x4c26  ldc.i4.3
0x4c27  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x4c2c  ldstr    a600// "600"
0x4c31  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4c36  dup
0x4c37  ldc.i4.4
0x4c38  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x4c3d  ldstr    aGetPutPostPatc// "GET, PUT, POST, PATCH, DELETE"
0x4c42  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4c47  dup
0x4c48  ldc.i4.5
0x4c49  box      Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x4c4e  ldstr    asc_7C08// ""
0x4c53  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::AddDefault(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> defaults, class [mscorlib]System.Enum configKey, string configValue)
0x4c58  stsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::_current
0x4c5d  ret
```
